Engage Digital Messaging - Android
==================================

Engage Digital provides a mobile messaging component that allows users of your app to easily communicate with your customer support agents. You can send text messages
and receive push notifications and automatic server-provided replies.

The component integrates nicely in any Android phone or tablet, allows presenting Engage Digital Messaging through Fragment or Activity and has rich customization options to fit
perfectly in your application.

For more information about Engage Digital Messaging, please see [Engage Digital Messaging reference](http://mobile-messaging.dimelo.com)


API Reference
-------------

Please refer to [Engage Digital Messaging SDK Android API Reference](https://rawcdn.githack.com/ringcentral/engage-digital-messaging-android/7d284444a3704d0faa72c1aa6ba24975fb81a90c/JavaDoc/index.html) for advanced use.

Supported Versions
------------------

The Engage Digital Messaging SDK Android is currently supporting **Android 4.4 (API 19) and above**.


Getting Started
---------------

Follow these three **mandatory** steps to integrate the Engage Digital Messaging in your application:

1. [Install the Engage Digital Messaging library using Gradle](#how-to-install-with-gradle-build-system-using-android-studio).
2. [Choose your authentication method and initialize the SDK](#authentication-and-sdk-initialization).
3. [Display Engage Digital Messaging in your application](#displaying-the-mobile-messaging).

#### **Note: Specify requirement for Apache HTTP Legacy library for Engage Digital Messaging version < 1.7.1**
If your app is targeting API level 28 (Android 9.0) or above, you must include the following declaration within the ```<application>``` element of ```AndroidManifest.xml```.

```xml
<uses-library
      android:name="org.apache.http.legacy"
      android:required="false" />
```

\
These are minimal steps to make Engage Digital Messaging work in your app.\
Read on how to customize the appearance and the behavior of Engage Digital Messaging to perfectly fit in your app:
- [Add the right permissions to your application](#add-the-right-permissions-to-your-application)
- [Customize Engage Digital Messaging appearance](#customizing-mobile-messaging-appearance)
- [Add push notifications support](#push-notifications)
- [Enable location messages using the Google APIs](#enable-location-messages)
- [Enable static maps display for location messages](#enable-static-maps-for-location-messages)
- [Add a listener to react to SDK triggered events](#reacting-to-mobile-messaging-events)

You can see an example of Engage Digital Messaging implementation by downloading the [Sample App](https://github.com/ringcentral-tutorials/engage-digital-messaging-android-demo).


How To Install With Gradle build system (Using Android Studio)
--------------------------------------------------------------

Add these to your Grade file:

### Repositories
```java
repositories {
    maven {
        url "https://raw.github.com/ringcentral/engage-digital-messaging-android/master"
    }
}
```

### Dependencies
```java
dependencies {
    compile 'com.dimelo.dimelosdk:dimelosdk:2.1.0'
}
```


Migration to Engage Digital Messaging 1.7.0
-------------------------------------------
Engage Digital Messaging 1.7.0 uses a new mandatory domain name setting (first part of your RingCentral Engage Digital URL: **domain-name**.engagement.dimelo.com), so these changes **must** be taken into consideration:
* `setApiSecret(String apiSecret)` is now deprecated in favor of `initWithApiSecret(String secret, String domainName, DimeloListener dimeloListener)`.
* `setApiKey(String apiKey)` is now deprecated in favor of `initWithApiKey(String apiKey, String domainName, DimeloListener dimeloListener)`.
* `setHostname(String  hostname)` is not available anymore.


Migration to Engage Digital Messaging 2.1.0
-------------------------------------------
To support multi threads in Engage Digital Messaging 2.1.0, these changes **must** be taken into consideration:
* When integrating the SDK as a fragment:
    - `newChatFragment()` method has been removed in favor of the new `newRcFragment()` method.
    - `Chat` type has been removed in favor of the new `RcFragment` type.
    - `newRcFragment()` method will either instantiate the chat or the conversations list based on the threading activation/deactivation.
    - To customize the conversations list or the chat, use `RcFragment.Customization` (`Chat.Customization` will no longer be available).
* When integrating the SDK as an activity:
    - `setOnActivitySetupAppearenceListener.onSetupAppearance` now expects a `RcFragment.Customization` to be passed as argument (it was previously expecting a `Chat.Customization`).


Authentication and SDK initialization
-------------------------------------

With each HTTP request, Engage Digital Messaging sends a JWT ([JSON Web Token](http://self-issued.info/docs/draft-ietf-oauth-json-web-token.html)).
This token contains user-specific info that you specify (`userIdentifier`, `userName`, `company`,`email`, `lastname`, `firstname`, `homePhone`, `mobilePhone`, etc.) and a HMAC signature. User identifier allows Engage Digital to identify author of messages from different in the agent's backend.
If user identifier is missing (`null`), then an autogenerated unique installation identifier is used to identify the user (created automatically).

If your app rely on a uniq imutable technical identifier to identify user use `userIdentifier` to also identify them at the Agent interface level.

Use `userName` to provide to agent a human name for the user.

Use `company` to provide to agent a company for the user.

Use `email` to provide to agent an email for the user.

Use `firstname` to provide to agent a first name for the user.

Use `lastname` to provide to agent a last name for the user.

Use `homePhone` to provide to agent a home phone for the user.

Use `mobilePhone` to provide to agent a mobile phone for the user.

We support two kinds of authentication modes: with **adhoc JWT signing** (less security) and with a **remote JWT signing** (recommended).

#### 1. Adhoc JWT signing

<details>
  <summary>Using an API secret (deprecated in version <code>3.2.0</code>)</summary>

  This is a convenient mode for testing and secure enough when user identifiers are unpredictable.

  Here's how to create the Dimelo instance and initialize it using a built-in secret:
  ```java
  Dimelo dimelo = Dimelo.setup(Context);
  dimelo.initWithApiSecret(SOURCE_API_SECRET, DIMELO_DOMAIN_NAME, DIMELO_LISTENER);
  /*
  SOURCE_API_SECRET can be found in your source configuration
  DIMELO_DOMAIN_NAME is your Dimelo Digital domain name (e.g. if your Dimelo Digital url is "DIMELO_DOMAIN_NAME.engagement.dimelo.com", then your domainName will be "DIMELO_DOMAIN_NAME")
  DIMELO_LISTENER is an optionnal parameter that we will cover later in this document
  */
  ```

  *Note:* To support hostname configuration, here's how to create the Dimelo instance and initialize it using a built-in secret:

  Here's how to create the Dimelo instance and initialize it using a built-in secret:
  ```java
  Dimelo dimelo = Dimelo.setup(Context);
  dimelo.initializeWithApiSecretAndHostName(SOURCE_API_SECRET, DIMELO_HOST_NAME, DIMELO_LISTENER);
  /*
  SOURCE_API_SECRET can be found in your source configuration
  DIMELO_HOST_NAME is your hostname (e.g. if your Dimelo Digital url is "DIMELO_DOMAIN_NAME.engagement.dimelo.com", then your hostName will be "DIMELO_DOMAIN_NAME.messaging.dimelo.com")
  DIMELO_LISTENER is an optionnal parameter that we will cover later in this document
  */
  ```

  Then it will create and sign JWT automatically when needed (as if it was provided by the server).

  You simply set necessary user-identifying information and JWT will be computed on the fly.
  You do not need any cooperation with your server in this setup.

  The security issue here is that built-in secret is rather easy to extract from the app's binary build.
  Anyone could then sign JWTs with arbitrary user identifying info to access other users'
  chats and impersonate them. To mitigate that risk make sure to use this mode
  only during development, or ensure that user identifiers are not predictable (e.g. random UUIDs).
</details>

<details open>
  <summary>Using a token (added in version <code>3.2.0</code>)</summary>

  Here's how to create the Dimelo instance and initialize it with a token, a JWT key ID and a JWT secret:
  ```java
  Dimelo dimelo = Dimelo.setup(Context);
  dimelo.initializeWithToken(token, hostname, jwtKeyId, jwtSecret, dimeloListener);
  ```

  |Parameter  |Description |
  | --------- | ---------- |
  |`token`    |can be found in your Engage Messaging channel administration page|
  |`hostname` |can be found in your Engage Messaging channel administration page|
  |`jwtKeyId` |can be found in your Engage Messaging community administration page|
  |`jwtSecret`|can be found in your Engage Messaging community administration page|
  |`delegate` |optional parameter that will be covered later in this document|

  Then it will create and sign JWT automatically when needed (as if it was provided by the server).

  You simply set necessary user-identifying information and JWT will be computed on the fly.
  You do not need any cooperation with your server in this setup.

  > [!WARNING]
  > The security issue here is that built-in secret is rather easy to extract from the app's binary build.
  > Anyone could then sign JWTs with arbitrary user identifying info to access other users'
  > chats and impersonate them. To mitigate that risk make sure to use this mode
  > only during development, or ensure that user identifiers are not predictable (e.g. random UUIDs).
</details>

#### 2. Remote JWT signing

<details>
  <summary>Using the public API key (deprecated in version <code>3.2.0</code>)</summary>

  This is a more secure mode. Dimelo will provide you with two keys: a public API key and a secret key.
  The public one will be used to configure `Dimelo` instance and identify your app.
  The secret key will be stored on your server and used to sign JWT token on your server.

  Here's how create the Dimelo instance and initialize it using a server-side secret:
  ```java
  Dimelo dimelo = Dimelo.setup(Context);
  dimelo.initWithApiKey(SOURCE_API_KEY, DIMELO_DOMAIN_NAME, DIMELO_LISTENER);
  /*
    SOURCE_API_KEY can be found in your source configuration
    DIMELO_DOMAIN_NAME is your Dimelo Digital domain name (e.g. if your Dimelo Digital url is "DIMELO_DOMAIN_NAME.engagement.dimelo.com", then your domainName will be "DIMELO_DOMAIN_NAME")
    DIMELO_LISTENER is an optionnal parameter that we will cover later in this document
  */
  ```

  *Note:* To support hostname configuration, here's how to create the Dimelo instance and initialize it using a server-side secret:

  ```java
  Dimelo dimelo = Dimelo.setup(Context);
  dimelo.initializeWithApiKeyAndHostName(SOURCE_API_KEY, DIMELO_HOST_NAME, DIMELO_LISTENER);
  /*
    SOURCE_API_KEY can be found in your source configuration
    DIMELO_HOST_NAME is your hostname (e.g. if your Dimelo Digital url is "DIMELO_DOMAIN_NAME.engagement.dimelo.com", then your hostName will be "DIMELO_DOMAIN_NAME.messaging.dimelo.com")
    DIMELO_LISTENER is an optionnal parameter that we will cover later in this document
  */
  ```

  Once this is done you will have to set `jwt` property manually with a value received from your server.
  This way your server will prevent one user from impersonating another.

  1. Set authentication-related properties (`userIdentifier`, `userName`, `company`, `email`, `lastname`, `firstname`, `homePhone`, `mobilePhone`, `authenticationInfo`).
  2. Get a dictionary for JWT using `Dimelo.getJwtDictionary()`. This will also contain public API key, `installationIdentifier` etc.
  3. Send this dictionary to your server.
  4. Check the authenticity of the JWT dictionary on the server and compute a valid signed JWT token.
  Use a corresponding secret API key to make a HMAC-SHA256 signature.
  *Note:* use raw binary value of the secret key (decoded from hex) to make a
  signature. Using hex string as-is will yield incorrect signature.
  5. Send the signed JWT string back to your app.
  6. In the app, set the `Dimelo.jwt` property with a received string.

  /!\ `Dimelo.setUserIdentifier();`, `Dimelo.setAuthenticationInfo();`, `Dimelo.setUserName();`, `Dimelo.setCompany();`, `Dimelo.setEmail();`, `Dimelo.setFirstname();`, `Dimelo.setLastName();`, `Dimelo.setHomePhone();`, and `Dimelo.setMobilePhone();` must only be called **BEFORE** `Dimelo.setJwt();` otherwise your JWT will be emptied and your request will end up in a 404 error.

  You have to do this authentication only once per user identifier,
  but before you try to use Engage Digital Messaging. Your application should prevent
  user from opening Engage Digital Messaging until you receive a JWT token.
</details>

<details open>
  <summary>Using a token (added in version <code>3.2.0</code>)</summary>

  This is a more secure mode.

  Here's how create the Dimelo instance and initialize it using a server-side signed JWT:
  ```java
  Dimelo dimelo = Dimelo.setup(Context);
  dimelo.initializeWithToken(token, hostname, dimeloListener);
  ```


  |Parameter  |Description |
  | --------- | ---------- |
  |`token`    |can be found in your Engage Messaging channel admin page|
  |`hostname` |can be found in your Engage Messaging channel admin page|
  |`delegate` |optional parameter that will be covered later in this document|

  Once this is done you will have to set `jwt` property manually with a value received from your server.
  This way your server will prevent one user from impersonating another.

  1. Set user-related properties (`userIdentifier`, `userName`, `company`,`email`, `lastname`, `firstname`, `homePhone`, `mobilePhone`, `authenticationInfo`).
  2. Get the JWT payload by calling `Dimelo.getJwtDictionary()`.
  It will return a `JSONObject` that contains the user-related properties set in the previous step as well as the `token` and an `installationId` (both of these are really important and should not be omitted).
  3. Send this dictionary to your server.
  4. Check the authenticity of the JWT payload on the server and compute a signed JWT.
  You will find your JWT secret and JWT key ID (required for the JWT signature) in:
      - Your Engage Messaging channel admin page (for RingCX users).
      - Your Engage Messaging commnity profile admin page (for Engage Digital users).

      :warning: The JWT **must** be signed using the JWT secret and **must** include the JWT key ID as the `kid` in the JWT header.

      :information_source: Please note that we currently only support HS256 and RS256 algorithms.
  5. Send the signed JWT string back to your app.
  6. In the app, set the `Dimelo.jwt` property with a received string.

  :warning: `Dimelo.setUserIdentifier();`, `Dimelo.setAuthenticationInfo();`, `Dimelo.setUserName();`, `Dimelo.setCompany();`, `Dimelo.setEmail();`, `Dimelo.setFirstname();`, `Dimelo.setLastName();`, `Dimelo.setHomePhone();`, and `Dimelo.setMobilePhone();` must only be called **BEFORE** `Dimelo.setJwt();` otherwise your JWT will be emptied and your request will end up in a 404 error.

  You have to do this authentication only once per user identifier,
  but before you try to use Engage Digital Messaging. Your application should prevent
  user from opening a Mobile Messaging until you receive a JWT token.
</details>


Enable/disable multi threads (supported in version 2.1.0)
---------------------------------------------------------

Use `enableThreads` flag to enable/disable multi threads.

Must be a boolean, default is `NO`.

Programmatically: set `Dimelo.enableThreads` property


Displaying Engage Digital Messaging
-----------------------------------

Dimelo provides different ways to display Engage Digital Messaging.

#### As an Activity:

Achieved by calling `Dimelo.openRcActivity()` (wich will internally call `Context.startActivity`).
This method will display a full screen Engage Digital Messaging with a Toolbar containing a title.
The title and the background (drawable or color) of the Toolbar are customizable.
The Navigation Icon can be displayed and customized.
The user can close Engage Digital Messaging (the Activity) by pressing the Navigation Icon or the back button of his device.

By default, the app name is used for the title and the primaryColor (appCompat) is used as the background color of the toolbar.

To make it work, you **must** declare the Activity in your `AndroidManifest.xml` with a name equals to `com.dimelo.dimelosdk.main.ChatActivity` and another one with a name equals to `com.dimelo.dimelosdk.main.ThreadsListActivity` when multi threads are enabled.
This is the easiest way to display Engage Digital Messaging.

If your application doesn't inherit from `AppCompat`, the toolbar and status bar of `Dimelo` will be black.
In order to fix this, your application needs to set the `ChatActivity` and `ThreadsListActivity` (when multi threads are enabled) theme to `@style/DimeloTheme` (`AndroidManifest.xml`).
By default, DimeloTheme will set the Toolbar and status bar to blue.

You can change those by overriding `dimelo_color_primary` and `dimelo_color_primary_dark` in color file resources (`dimelo_color_primary` for toolbar and `dimelo_color_primary_dark` for status bar).

*Note:* This is an example on how to declare Engage Digital Messaging activities in `AndroidManifest.xml`:
- When threading is enabled:

```xml
<activity android:name="com.dimelo.dimelosdk.main.ChatActivity" />

<activity android:name="com.dimelo.dimelosdk.main.ThreadsListActivity">
  <meta-data
    android:name="android.support.PARENT_ACTIVITY"
    android:value="com.dimelo.sampleapp.MainActivity" />
</activity>

...
```

- When threading is disabled:

```xml
<activity android:name="com.dimelo.dimelosdk.main.ChatActivity">
  <meta-data
    android:name="android.support.PARENT_ACTIVITY"
    android:value="com.dimelo.sampleapp.MainActivity" />
</activity>

...
```

#### As a Fragment:

Your app must use an `AppCompat` theme to be able to use `Dimelo` as a `Fragment`.
Achieved by calling `Dimelo.newRcFragment()` and using the Android `FragmentManager` and `FragmentTransaction`.
This is the most flexible way to display Engage Digital Messaging as you can manually place, open and close it like any Fragment.
No Toolbar is displayed.

##### Note: The dimelo Fragment is renamed to `RcFragment` and it will instantiate the `Chat` or the `ThreadsListFragment` according to the activation/deactivation of threads.

##### Note: forwarding onBackPressed() events using "RcFragment.onBackPressed()" is necessary to display the best user experience; "true" will be returned if the event has been consumed


#### As a Nested Fragment:
Engage Digital Messaging support fragment nesting (i.e: Engage Digital Messaging fragment can be displayed inside a fragment parent).
However, in this specific case, the host application needs to care about the following steps.

1. Using Fragment.setUserVisibleHint in order to notify Engage Digital Messaging about its visibility state.
This will prevent Engage Digital Messaging to do background work when unnecessary

2. Engage Digital Messaging uses intents for displaying attachments. Forwarding "onActivityResult" will allow Engage Digital Messaging to correctly receive the results.

3. Engage Digital Messaging is compiled against Android sdk 23 and handle dynamic permissions.
To allow optimal behaviors, forwarding "onRequestPermissionsResult" is necessary.

##### Note: forwarding onBackPressed() events using "RcFragment.onBackPressed()" is necessary to display the best user experience; "true" will be returned if the event has been consumed

Examples are provided within the SampleApp


Localization
------------

Please refer to [Localization.md](Localization.md) for guidance on strings customization


Add the right permissions to your application
---------------------------------------------

### Camera

#### Android 11+

In order for the camera to be enabled you'll need to add the `CAMERA` permission to your `AndroidManifest.xml`:
```xml
<uses-permission android:name="android.permission.CAMERA" />
```

#### Android < 11

Just like in Android 11+ you'll need to add the `CAMERA` permission to your `AndroidManifest.xml` but you'll also need to add the `WRITE_EXTERNAL_STORAGE` permission:
```xml
<uses-permission android:name="android.permission.CAMERA" />
<uses-permission android:name="android.permission.WRITE_EXTENAL_STORAGE" />
```



Customizing Engage Digital Messaging Appearance
-----------------------------------------------

[See how to customize Engage Digital Messaging using the Android Resource folders](Customization.md).

You can also customize it programmatically:
#### As an Activity:
- Implementing `Dimelo.OnActivitySetupAppearanceListener(RcFragment.Customization customization)` and modifying `customization` attributes.

The ThreadsListActivity/ChatActivity will call the listener back when creating its layout.

You do not need to call customization.apply() as it will be called for you.

#### As a Fragment:
1) Calling `RcFragment.getCustomization()` and receiving an instance of `RcFragment.Customization`
2) Modifiying its attributes.
3) Calling customization.apply() to register the changes and update Engage Digital Messaging.

We provide a lot of properties for you to make Engage Digital Messaging look native to your application.

For your convenience, properties are organized in two groups: Basic and Advanced.
In many cases it would be enough to adjust the Basic properties only.

You can customize the inputbar color, the font and the color of any text in Engage Digital Messaging view.
If you are displaying Engage Digital Messaging as an activity you can also cutomize the ActionBar colors and title

Advanced options include background and padding for text bubbles.
We use 3 kinds of messages. Each kind can be customized independently.

1. User's text message.
3. Agent's text message.
3. System text notification (automatic reply from the server).

All bubble images must be 9-part sliced resizable images or a ([Drawable xml](http://developer.android.com/guide/topics/resources/drawable-resource.html)) to fit arbitrary content.

Text bubbles can be colored using properties `userMessageBackgroundColor`, `agentMessageBackgroundColor` etc.

If you provide a custom bubble image for text, you should also update
message bubble padding properties to arrange your text correctly within a bubble.

Check the [Engage Digital Messaging SDK Android API Reference](https://rawcdn.githack.com/ringcentral/engage-digital-messaging-android/7d284444a3704d0faa72c1aa6ba24975fb81a90c/JavaDoc/index.html) to learn about all customization options.


Push Notifications
------------------

Engage Digital Messaging can receive push notifications from Engage Digital Messaging server.
To make them work, a couple of steps must be done on your part:

### Using Google Cloud Messaging (GCM):
1. Register to Google GCM service by using for example `GoogleCloudMessaging.register(senderId)`
2. Set `Dimelo.deviceToken` property with the value returned by the `GoogleCloudMessaging.register(senderId)`
3. Your app must register for remote notifications for example by declaring and implementing a `Receiver` and a `Service` (Android APIs).
4. Optionally implement `Dimelo.BasicNotificationDisplayer` abstract class.
   It allows you to specify a title, an icone and how to display Engage Digital Messaging when the user click the notification.
   If you want to handle the entire process of displaying notifications you can directly implement `Dimelo.NotificationDisplayer` interface.
5. Let Dimelo consume the notification using `Dimelo.consumeReceivedRemoteNotification()`.
   If this method returns `true`, it means that Dimelo recognized the notification as its own and you should not
   process the notification yourself. Engage Digital Messaging will be updated automatically with a new message.
6. If your Android version is at least Android N, you'll receive an interactive push notification with direct reply. To disable this, use `Dimelo.interactiveNotification = false;`.

If the notification is received while the app is running, the sdk will display the notification only if Engage Digital Messaging is not visible by the user
You can override the behavior by implementing `dimeloShouldDisplayNotificationWithText` from the listener `DimeloListener`

Prior to Android 5, the notification will be displayed as a Ticker (one line scrolling notification) and is not clickable.

Starting from Android 5, the notification will be displayed as a ([Heads-up](http://developer.android.com/guide/topics/ui/notifiers/notifications.html#Heads-up)).
Clicking of the Heads-up will, by default, open the application.
If you specify the ([parent activity using the support meta-data tag](http://developer.android.com/training/implementing-navigation/ancestral.html)), clicking the Heads-up will open Engage Digital Messaging and provide the up-navigation.

If Engage Digital Messaging is opened directly upon clicking the notification, then the `IntentService` managing the notification must ensure to properly configure the `Dimelo` instance (at the minimum, calling `Dimelo.setup` and `dimelo.setApiSecret`).

If you'd like to have the full control on the notification (appearance and behavior on click) you can implement the `Dimelo.NotificationDisplayer` interface.

<br>

### Using [Firebase Cloud Messaging](https://firebase.google.com/docs/cloud-messaging/android/client) (FCM):
*Note:* This is an example on how to initialize the Dimelo instance:
```java
public class MainActivity extends AppCompatActivity {
    public static Dimelo setupDimelo(Context context) {
        Dimelo.setup(context);
        Dimelo dimelo = Dimelo.getInstance();

        dimelo.initWithApiSecret(CHANNEL_API_SECRET, ENGAGE_DIGITAL_DOMAIN_NAME, DIMELO_LISTENER);
        dimelo.setPushNotificationService("fcm");
        return dimelo;
    }

    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.your_layout);
        // Setup Dimelo
        Dimelo dimelo = setupDimelo(this);
    }

    ...
}
```
1. Download the `google-services.json` file from your [firebase console](https://support.google.com/firebase/answer/7015592) and copy it in your project's `/app` folder
2. Declare a `FirebaseMessagingService` [service](https://firebase.google.com/docs/reference/android/com/google/firebase/messaging/FirebaseMessagingService) in your project's `AndroidManifest.xml`:
```xml
<service
    android:name=".MyFirebaseMessagingService">
    <intent-filter>
        <action android:name="com.google.firebase.MESSAGING_EVENT"/>
    </intent-filter>
</service>
```
3. Create a class that extends FirebaseMessagingService:
```java
public class MyFirebaseMessagingService extends FirebaseMessagingService
```
4. Retrieve the device token and pass it to your Dimelo instance by overriding the `onNewToken` method:
```java
@Override
public void onNewToken(String token) {
    if (Dimelo.isInstantiated())
        Dimelo.getInstance().setDeviceToken(token);
}
```
5.  Finally intercept the notification and pass it to your Dimelo instance by overring the `onMessageReceived` method:
```java
@Override
public void onMessageReceived(RemoteMessage remoteMessage) {
    // You have to configure the Dimelo instance before calling the Dimelo.consumeReceivedRemoteNotification() method.
    MainActivity.setupDimelo(MyFirebaseMessagingService.this);
    if (Dimelo.consumeReceivedRemoteNotification(MyFirebaseMessagingService.this, remoteMessage.getData(), null)){
        // The notification will be handled by the Dimelo instance
    }
    else {
        // It is not a Dimelo notification.
    }
}
```

*Note:* You can also retrieve the current device token by calling `FirebaseInstanceId.getInstance().getInstanceId()`. Here is an example on how to retrieve the device token and pass it to the Dimelo instance (as [described here](https://firebase.google.com/docs/cloud-messaging/android/client#retrieve-the-current-registration-token)):
```java
FirebaseInstanceId.getInstance().getInstanceId()
        .addOnCompleteListener(new OnCompleteListener<InstanceIdResult>() {
            @Override
            public void onComplete(@NonNull Task<InstanceIdResult> task) {
                if (!task.isSuccessful()) {
                    Log.w(TAG, "getInstanceId failed", task.getException());
                    return;
                }

                // Get new Instance ID token
                String token = task.getResult().getToken();
                Dimelo.getInstance().setDeviceToken(token);
            }
        });
```

<br>

### Using [Huawei Push Kit](https://developer.huawei.com/consumer/en/doc/development/HMSCore-Guides/android-app-quickstart-0000001071490422) (HMS):
*Note:* This is an example on how to initialize the Dimelo instance:
```java
public class MainActivity extends AppCompatActivity {
    public static Dimelo setupDimelo(Context context) {
        Dimelo.setup(context);
        Dimelo dimelo = Dimelo.getInstance();
        dimelo.initWithApiSecret(CHANNEL_API_SECRET, ENGAGE_DIGITAL_DOMAIN_NAME, DIMELO_LISTENER);
        dimelo.setPushNotificationService("hms");
        return dimelo;
    }

    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.your_layout);
        // Setup Dimelo
        Dimelo dimelo = setupDimelo(this);
    }

    ...
}
```

1. Add `Dimelo.setPushNotificationService("hms")` to your rc configuration to support the Huawei push notifications (Default is `fcm`)
2. Configuring App Information in [AppGallery Connect](https://developer.huawei.com/consumer/en/doc/development/HMSCore-Guides/android-config-agc-0000001050170137)
- Sign in to AppGallery Connect and click My projects.
- Find your app project and click the app that needs to integrate the HMS Core SDK.

<p align="center">
  <img src="https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20210802090814.80931510641674637684723202830368:50520801015821:2800:FF259F927F95CBD1CD9152A63AF4D20D9BEC1063B202121BBFE1A8B6D2D67383.png?needInitFileName=true?needInitFileName=true"/>
</p>

3. Download the `agconnect-services.json` file from your [AppGallery Connect](https://developer.huawei.com/consumer/en/doc/development/quickApp-Guides/quickapp-get-agconnectfile-0000001117853750) and copy it in your project's `/app` folder

<p align="center">
  <img src="https://i.postimg.cc/hjCJ2mHm/agconnect-services.png"/>
</p>

4. Configuring the Maven Repository Address for the [HMS Core SDK](https://developer.huawei.com/consumer/en/doc/development/HMSCore-Guides/android-integrating-sdk-0000001050040084#section813910382284)
- Add the AppGallery Connect plugin and the Maven repository.
- Go to buildscript > repositories and configure the Maven repository address for the HMS Core SDK.
- Go to allprojects > repositories and configure the Maven repository address for the HMS Core SDK.
- If the agconnect-services.json file has been added to the app, go to buildscript > dependencies and add the AppGallery Connect plugin configuration.
```java
buildscript {
    repositories {
        google()
        jcenter()

        // Configure the Maven repository address for the HMS Core SDK.
        maven { url 'https://developer.huawei.com/repo/' }
    }
    dependencies {
        ...

        // Add the AppGallery Connect plugin configuration.
        classpath 'com.huawei.agconnect:agcp:1.4.2.300'
    }
}

allprojects {
    repositories {
        google()
        jcenter()

        // Configure the Maven repository address for the HMS Core SDK.
        maven { url 'https://developer.huawei.com/repo/' }
    }
}
```
5. Add the [build dependencies](https://developer.huawei.com/consumer/en/doc/development/HMSCore-Guides/android-integrating-sdk-0000001050040084#section12051333182410)
- Add a build dependency in the dependencies block.
```java
dependencies {
    implementation 'com.huawei.hms:push:{version}'
}
```
- Add the AppGallery Connect plugin configuration:
```java
apply plugin: 'com.huawei.agconnect'
```
6. Configure the signing information in the build.gradle File https://developer.huawei.com/consumer/en/doc/development/HMSCore-Guides/android-integrating-sdk-0000001050040084
- Copy the keystore file generated in Generating a Signing Certificate Fingerprint to the app directory of your project and configure the signing information in the build.gradle file in the directory.
```java
android {
    signingConfigs {
        config {
            // Set the parameters based on the actual signing information.
            keyAlias 'xxx'
            keyPassword 'xxxx'
            storeFile file('xxx.jks')
            storePassword 'xxxx'
        }
    }
    buildTypes {
        debug {
            signingConfig signingConfigs.config
        }

        release {
            signingConfig signingConfigs.config
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'
        }
    }
 }
 ```
7. set the `minSdkVersion` to 17 or above in the build.gradle File
8. Declare a `HmsMessageService` [service](https://developer.huawei.com/consumer/en/doc/development/HMSCore-References/hmsmessageservice-0000001050173839) in your project's `AndroidManifest.xml`:
```xml
<service
    android:name=".MyHmsMessageService"
    android:exported="false">
    <intent-filter>
        <action android:name="com.huawei.push.action.MESSAGING_EVENT" />
    </intent-filter>
</service>
```
9. Declare a `push_kit_auto_init_enabled` meta data (https://developer.huawei.com/consumer/en/doc/development/HMSCore-Guides/android-client-dev-0000001050042041) in your project's `AndroidManifest.xml`:
```xml
<manifest ...>
...
    <application ...>
        <meta-data
            android:name="push_kit_auto_init_enabled"
            android:value="true"/>
        ...
    </application>
...
</manifest>
```

10. Create a class that extends `HmsMessageService`:
```java
public class MyHmsMessageService extends HmsMessageService
```

11. Retrieve the device token and pass it to your Dimelo instance by overriding the `onNewToken` method if `push_kit_auto_init_enabled=true`:
```java
@Override
public void onNewToken(String token) {
    if (Dimelo.isInstantiated())
        Dimelo.getInstance().setDeviceToken(token);
}
```

12. Finally intercept the notification and pass it to your Engage Digital Messaging SDK by overriding the `onMessageReceived` method:
```java
@Override
public void onMessageReceived(RemoteMessage remoteMessage) {
    // You have to configure the Dimelo instance before calling the Dimelo.consumeReceivedRemoteNotification() method.
    MainActivity.setupDimelo(MyFirebaseMessagingService.this);
    if (Dimelo.consumeReceivedRemoteNotification(MyHmsMessageService.this, remoteMessage.getDataOfMap(), null)){
        // The notification will be handled by the Engage Digital Messaging SDK
    }
    else {
        // It is not a RingCentral Engage Digital Messaging notification.
    }
}
```

*Note:* You can also retrieve the current device token by calling `HmsInstanceId.getInstance(Context).getToken(appId, tokenScope)` if `push_kit_auto_init_enabled=false`. Here is an example on how to retrieve the device token and pass it to the Dimelo instance (as [described here](https://developer.huawei.com/consumer/en/doc/development/HMSCore-Guides/android-client-dev-0000001050042041#section11455525765)):

```java
private void getToken() {
    new Thread() {
        @Override
        public void run() {
            try {
                String appId = "your_app_gallery_connect_app_id";
                String tokenScope = "HCM";
                String token = HmsInstanceId.getInstance(MainActivity.this).getToken(appId, tokenScope);

                if (!TextUtils.isEmpty(token) && Dimelo.isInstantiated()) {
                    Dimelo.getInstance().setDeviceToken(token);
                }
            } catch (ApiException e) {}
        }
    }.start();
}
```

*Note:* With Android 13: you'll need to add the `POST_NOTIFICATIONS` permission in your `AndroidManifest.xml` file then accept the alert dialog to continue receiving push notifications:
```xml
<uses-permission android:name="android.permission.POST_NOTIFICATIONS" />
```

Enable location messages
------------------------
Please refer to the [Engage Digital Messaging Maps SDK for Android documentation](https://github.com/ringcentral/engage-digital-messaging-android-location) for guidance on how to allow your users to send location messages (only compatible with **version 2.3.0 and above**).

Enable static maps for location messages
----------------------------------------
Along with allowing your users to send location messages through the Engage Digital Messaging SDK you can also allow your users to see the location they sent as [a static map generated using Google's APIs](https://developers.google.com/maps/documentation/maps-static/overview)

Here are the step you need to follow in order to enable this feature:
1. Generate a Google API key with the [**Maps Static API**](https://developers.google.com/maps/documentation/maps-static/overview) enabled
2. Provide the API key to your `Dimelo` instance:
```java
Dimelo dimelo = Dimelo.getInstance();
dimelo.setStaticMapsApiKey("YOUR_API_KEY");
```

Please note that if the API key is not present or if it doesn't have the correct permission to display a static map we'll only display a link to Google Maps containing the address that was sent by the user.

Reacting To Engage Digital Messaging Events
-------------------------------------------

You can react to various events in Engage Digital Messaging by implementing a `DimeloListener`.

Two particular events that might be interesting to you are `dimeloDidBeginNetworkActivity()` and `dimeloDidEndNetworkActivity()`.

Use `onOpen(Dimelo dimelo)` and `onClose(Dimelo dimelo)` events to get informations using `dimelo` parameter when Engage Digital Messaging view is just opened or closed.

You can use the `rcShouldDelegateUrlOpening(URI uri)` event that will be fired by `DimeloListener` when a URL is going to be opened by the Engage Digital Messaging Android SDK:
- return `false` to let the Engage Digital Messaging Android SDK open the URL.
- return `true` to prevent the Engage Digital Messaging Android SDK from opening the URL so that you can apply your own logic.

Please refer to [Engage Digital Messaging SDK Android API Reference](https://rawcdn.githack.com/ringcentral/engage-digital-messaging-android/7d284444a3704d0faa72c1aa6ba24975fb81a90c/JavaDoc/index.html) documentation for more information.


Enabling the camera in Android 11+
----------------------------------

Starting in Android 11, you must add the <queries> to your manifest application for the camera to work.

```xml
<queries>
   <intent>
     <action android:name="android.media.action.IMAGE_CAPTURE" />
   </intent>
</queries>
```


Manually opening a WebView
--------------------------

The Engage Digital Messaging Android SDK exposes the `openWebView(URL url, RC_WEB_VIEW_SIZE height)` method to allow you to manually open a WebView.

This method takes 2 parameters:
- The `url` parameter is a `URL` that represents the URL you want to open in the WebView.
- The `height` parameter is a `RC_WEB_VIEW_SIZE` that represents the height of the WebView (based on the WebView's container size), its value can be:

|Value|Container's height|
|-----|------------------|
|`FULL_MODE`|100%|
|`TALL_MODE`|75%|
|`COMPACT_MODE`|50%|
