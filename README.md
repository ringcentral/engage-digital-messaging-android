Dimelo-Android
==========

Dimelo provides a mobile messaging component that allows users of your app to easily communicate with your customer support agents. You can send text messages
and receive push notifications and automatic server-provided replies.

The component integrates nicely in any Android phone or tablet, allows presenting the chat through Fragment or Activity and has rich customization options to fit
perfectly in your application.

For more information about Dimelo Mobile, please see [Dimelo Mobile Messaging reference](http://mobile-messaging.dimelo.com)

Getting Started
---------------

Follow these steps to integrate the Dimelo Mobile Messaging in your application.

1. Install the Dimelo library via Gradle (see **How To Install With Gradle build system**).

2. Optional - Add a Google Map API Key (see **Activate location messages**)

3. Initialize the SDK with `Dimelo.setup(Context)`, configure it with your API secret (`dimelo.setApiSecret(secret)`), optional user identifier and other user-specific info. (See **Authentication** section)
You can also use the Android resources folder (res) to customize the appearance.
[See more informations about how to use the Android resources in order to configure Dimelo](ChatCustomization.md)

4. You can optionally specify a listener for `Dimelo` instance with `dimelo.setDimeloListener(listener)`
To display a chat, open it either as a Fragment `Dimelo.newChatFragment()` or as an Activity `Dimelo.openChatActivity()`.
If opening the chat as an Activity is your choice, you must declare it in your AndroidManifest with a name equals to `com.dimelo.dimelosdk.main.ChatActivity`
(See **Displaying the Mobile Messaging** section)

5. Setup a `Receiver`, a `Service` (Android APIs) and set `deviceToken` property on your `Dimelo` instance with `setDeviceToken()`.
This will allow your app to receive push notifications from the Dimelo server when your agent replies to a user.
See **Push Notifications** for more detail.

6. Also call `Dimelo.consumeReceivedRemoteNotification()` from your Service.

These are minimal steps to make your chat work in your app. Read on to learn how to customize the appearance and behaviour of the chat to fit perfectly in your app.

You can see an example by downloading the [Sample App](https://github.com/dimelo/Dimelo-Android-SampleApp).

Displaying the Mobile Messaging
-------------------

Dimelo provides different ways to display the chat.

#### As an Activity:

Achieved by calling `Dimelo.openChatActivity()` (wich will internally call `Context.startActivity`).
This method will display a full screen chat with a Toolbar containing a title.
The title and the background (drawable or color) of the Toolbar are customizable.
The Navigation Icon can be displayed and customized.
The user can close the chat (the Activity) by pressing the Navigation Icon or the back button of his device.

By default, the app name is used for the title and the primaryColor (appCompat) is used as the background color of the toolbar.

To make it work, you must declare the Activity in your `AndroidManifest.xml` with a name equals to `com.dimelo.dimelosdk.main.ChatActivity`
This is the easiest way to display the chat.

If your application doesn't inherit from `AppCompat`, the toolbar and status bar of `Dimelo` will be black.
In order to fix this, your application needs to set the `ChatActivity` theme to `@style/DimeloTheme` (`AndroidManifest.xml`).
By default, DimeloTheme will set the Toolbar and status bar to blue.

You can change those by overriding `dimelo_color_primary` and `dimelo_color_primary_dark` in color file resources (`dimelo_color_primary` for toolbar and `dimelo_color_primary_dark` for status bar).

#### As a Fragment:

Your app must use an `AppCompat` theme to be able to use `Dimelo` as a `Fragment`.
Achieved by calling `Dimelo.newChatFragment()` and using the Android `FragmentManager` and `FragmentTransaction`.
This is the most flexible way to display the chat as you can manually place, open and close it like any Fragment.
No Toolbar is displayed.
##### Note: forwarding onBackPressed() events using "Chat.onBackPressed()" is necessary to display the best user experience; "true" will be returned if the event has been consumed


#### As a Nested Fragment:
Dimelo support fragment nesting (i.e: Dimelo Chat fragment can be displayed inside a fragment parent).
However, in this specific case, the host application needs to care about the following steps.

1. Using Fragment.setUserVisibleHint in order to notify the chat about its visibility state.
This will prevent the chat to do background work when unnecessary

2. The chat uses intents for displaying attachments. Forwarding "onActivityResult" will allow the chat to correctly receive the results.

3. The chat is compiled against Android sdk 23 and handle dynamic permissions.
To allow optimal behaviors, forwarding "onRequestPermissionsResult" is necessary.

##### Note: forwarding onBackPressed() events using "Chat.onBackPressed()" is necessary to display the best user experience; "true" will be returned if the event has been consumed

Examples are provided within the SampleApp

Authentication
--------------

With each HTTP request, Dimelo sends a JWT ([JSON Web Token](http://self-issued.info/docs/draft-ietf-oauth-json-web-token.html)).
This token contains user-specific info that you specify (`userIdentifier`, `userName` etc.) and a HMAC signature. User identifier allows Dimelo to identify author of messages from different in the agent's backend.
If user identifier is missing (`null`), then an autogenerated unique installation identifier is used to identify the user (created automatically).

If your app rely on a uniq imutable technical identifier to identify user use `userIdentifier` to also identify them at the Agent interface level.

Use `userName` to provide to agent a human name for the user.

We support two kinds of authentication modes: with server-side secret and a built-in secret.

#### 1. Setup with a built-in secret

This is a convenient mode for testing and secure enough when user identifiers are unpredictable.

You configure `Dimelo` instance (`Dimelo.createInstance(context)`) with the *secret* key (`dimelo.setApiSecret(secret)`) and it creates and signs JWT automatically when needed (as if it was provided by the server).
You simply set necessary user-identifying information and JWT will be computed on the fly.
You do not need any cooperation with your server in this setup.

The security issue here is that built-in secret is rather easy to extract from the app's binary build.
Anyone could then sign JWTs with arbitrary user identifying info to access other users'
chats and impersonate them. To mitigate that risk make sure to use this mode
only during development, or ensure that user identifiers are not predictable (e.g. random UUIDs).

#### 2. Setup with a server-side secret (better security but more complicated)

This is a more secure mode. Dimelo will provide you with two keys: a public API key and a secret key.
The public one will be used to configure `Dimelo` instance and identify your app.
The secret key will be stored on your server and used to sign JWT token on your server.

When you configure Dimelo with a public API key (`initWithApiKey(hostname, listener)`),
you will have to set `jwt` property manually with a value received from your server.
This way your server will prevent one user from impersonating another.

1. Set authentication-related properties (`userIdentifier`, `userName`, `authenticationInfo`).
2. Get a dictionary for JWT using `Dimelo.getJwtDictionary()`. This will also contain public API key, `installationIdentifier` etc.
3. Send this dictionary to your server.
4. Check the authenticity of the JWT dictionary on the server and compute a valid signed JWT token.
Use a corresponding secret API key to make a HMAC-SHA256 signature.
*Note:* use raw binary value of the secret key (decoded from hex) to make a
signature. Using hex string as-is will yield incorrect signature.
5. Send the signed JWT string back to your app.
6. In the app, set the `Dimelo.jwt` property with a received string.

/!\ `Dimelo.setUserIdentifier();`, `Dimelo.setAuthenticationInfo();` and `Dimelo.setUserName();` must only be called **BEFORE** `Dimelo.setJwt();` otherwise your JWT will be emptied and your request will end up in a 404 error.

You have to do this authentication only once per user identifier,
but before you try to use Dimelo chat. Your application should prevent
user from opening a chat until you receive a JWT token.



Push Notifications
------------------

Dimelo chat can receive push notifications from Dimelo server.
To make them work, a couple of steps must be done on your part:

1. Register to Google GCM service by using for example `GoogleCloudMessaging.register(senderId)`
2. Set `Dimelo.deviceToken` property with the value returned by the `GoogleCloudMessaging.register(senderId)`
3. Your app must register for remote notifications for example by declaring and implementing a `Receiver` and a `Service` (Android APIs).
4. Optionally implement `Dimelo.BasicNotificationDisplayer` abstract class.
   It allows you to specify a title, an icone and how to display the chat when the user click the notification.
   If you want to handle the entire process of displaying notifications you can directly implement `Dimelo.NotificationDisplayer` interface.
5. Let Dimelo consume the notification using `Dimelo.consumeReceivedRemoteNotification()`.
   If this method returns `true`, it means that Dimelo recognized the notification as its own and you should not
   process the notification yourself. The chat will be updated automatically with a new message.
6. If your Android version is at least Android N, you'll receive an interactive push notification with direct reply. To disable this, use `Dimelo.interactiveNotification = false;`.

If the notification is received while the app is running, the sdk will display the notification only if the chat is not visible by the user
You can override the behavior by implementing `dimeloShouldDisplayNotificationWithText` from the listener `DimeloListener`

Prior to Android 5, the notification will be displayed as a Ticker (one line scrolling notification) and is not clickable.

Starting from Android 5, the notification will be displayed as a ([Heads-up](http://developer.android.com/guide/topics/ui/notifiers/notifications.html#Heads-up)).
Clicking of the Heads-up will, by default, open the application.
If you specify the ([parent activity using the support meta-data tag](http://developer.android.com/training/implementing-navigation/ancestral.html)), clicking the Heads-up will open the chat and provide the up-navigation.

If the chat is opened directly upon clicking the notification, then the `IntentService` managing the notification must ensure to properly configure the `Dimelo` instance (at the minimum, calling `Dimelo.setup` and `dimelo.setApiSecret`).

If you'd like to have the full control on the notification (appearance and behavior on click) you can implement the `Dimelo.NotificationDisplayer` interface.

Customizing Mobile Messaging Appearance
---------------------------

[see how to customize Dimelo using the Android Resource folders](ChatCustomization.md)

You can also customize it programmatically:
#### As an Activity:
1) Implementing `Dimelo.OnActivitySetupAppearanceListener(Chat.Customization chatActivityCustomization)` and modifying `chatActivityCustomization` attributes.
2) Calling Dimelo.setChatCustomizationListener()

The ChatActivity will call the listener back when creating its layout.

You do not need to call customization.apply() as it will be called for you.

#### As a Fragment:
1) Calling `Chat.getCustomization()` and receiving an istance of `Chat.Customization`
2) Modifiying its attributes.
3) Calling customization.apply() to register the changes and update the chat.

We provide a lot of properties for you to make the chat look native to your application.

For your convenience, properties are organized in two groups: Basic and Advanced.
In many cases it would be enough to adjust the Basic properties only.

You can customize the inputbar color, the font and the color of any text in the chat view.
If you are displaying the chat as an activity you can also cutomize the ActionBar colors and title

Advanced options include background and padding for text bubbles.
We use 3 kinds of messages. Each kind can be customized independently.

1. User's text message.
3. Agent's text message.
3. System text notification (automatic reply from the server).

All bubble images must be 9-part sliced resizable images or a ([Drawable xml](http://developer.android.com/guide/topics/resources/drawable-resource.html)) to fit arbitrary content.

Text bubbles can be colored using properties `userMessageBackgroundColor`, `agentMessageBackgroundColor` etc.

If you provide a custom bubble image for text, you should also update
message bubble padding properties to arrange your text correctly within a bubble.

Check the [Dimelo Mobile SDK Android API Reference](https://rawgit.com/dimelo/Dimelo-Android/master/JavaDoc/index.html) to learn about all customization options.


Reacting To Mobile Messaging Events
-----------------------

You can react to various events in the chat by implementing a `DimeloListener`.

Two particular events that might be interesting to you are `dimeloDidBeginNetworkActivity()` and `dimeloDidEndNetworkActivity()`.

Use `-onOpen:` and `-onClose:` events to get informations using `dimelo` parameter when the chat view is just opened or closed.

Please refer to [Dimelo Mobile SDK Android API Reference](https://rawgit.com/dimelo/Dimelo-Android/master/JavaDoc/index.html) documentation for more information.

How To Install With Gradle build system (Using Android Studio)
-----------------------------

Update your gradle file in three steps:

## repositories

	repositories {
 	   	maven {
        	      url "https://raw.github.com/dimelo/Dimelo-Android/master"
		}
	}

## dependencies
	dependencies {
    		compile 'com.dimelo.dimelosdk:dimelosdk:1.4.+'
	}

## :warning: ProGuard warnings
If you are using ProGuard during your compilation process you might get a lot of warnings caused by the Dimelo Mobile SDK.

In order to fix them you will need to tell ProGuard that the Dimelo dependency is fine and shouldn't trigger any warning, you can do so by adding the following lines to your ProGuard file:

    -dontwarn com.dimelo.**
    -dontwarn com.squareup.picasso.**

<a name="activate_location_messages"></a>Activate location messages
-----------------------------
Activating location messages allow users to send a map containing their location.

**Note**: This feature uses [Google Places API](https://developers.google.com/places/android-api/)  which is by default limited to 1000 requests per day. you can increase this limitation to 150 000 requests per day ([Enable billing to get 150 000 requests per 24 hour period](https://developers.google.com/places/android-api/usage#enable-billing))


1. Connect to [Google API console](https://console.developers.google.com/)
2. Access to API Manager pannel
3. Search for **Google Maps Android API** and **Google Places API for Android**
4. Enable both APIs
5. Access to Credentials pannel and create an API key for Android
6. Add your API key to your application manifest
```
<application
  <meta-data
	android:name="com.google.android.geo.API_KEY"
	android:value="YOUR_API_KEY">
</application>
```
Migration from Dimelo 1.0 to Dimelo 1.1
-----------------------------
Dimelo 1.1 brings attachement support (Gallery, Camera and Location) as well as dynamic permissions.

Here are the steps in order to migrate from 1.0 to 1.1


1. Update your dimelo gradle dependency:
> From 'com.dimelo.dimelosdk:dimelosdk:1.0.+' to 'com.dimelo.dimelosdk:dimelosdk:1.1.+'

2. Add dependency to RenderScript:
> DefaultConfig {
> renderscriptTargetApi 23
> renderscriptSupportModeEnabled true
> }

Note that RenderScript is no longer necessary after v1.4.4.

3. Forward callbacks:
To allow optimal behaviors, forwarding "onBackPressed" and "onRequestPermissionsResult" is necessary.

API Reference
-------------

Please refer to [Dimelo Mobile SDK Android API Reference](https://rawgit.com/dimelo/Dimelo-Android/master/JavaDoc/index.html) for advanced use.


