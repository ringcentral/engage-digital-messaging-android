# Dimelo Android master #

## Dimelo Android 1.9.2 (December 1st, 2020) ##
- Improvement: retry a few times and display the error icon when the internet is down. RD-10547
- Feature: add `dateFormatter` to customize the date format for the date label. RD-11359
- Feature: taping the error icon alongside a message now allows to retry the message sending request. RD-9309
- Feature: add support for the structured messages (quick reply, template, carousel and rich link). RD-12832:
    - add multiple customization keys ([listed in Customization.md](Customization.md))
    - the input accessory view is hidden when a quick reply disabling it is sent
    - support gif and deeplinks in structured messages
- Feature: new design. RD-12835:
    - support agent avatar (`showAgentAvatarImage = true | false` defaults to `true`)
    - add `hourTimeFont`, `hourTimeTextColor` and `hourTimeTextSize` keys to customize the hour part of the date
    - add `agentTimeFont`, `agentTimeColor`, `agentTimePadding` and `agentTimeTextSize` keys to customize the time next to the agent name
    - replace the current send button icon. Use the existing `sendButtonEnabledColor` (when active) and `sendButtonDisabledColor` keys to customize the send icon
    - add `rc_hint_input_text` localization key to customize the hint text in the input accessory view
    - add `rc_today` localization key for the date
    - automatically apply system date and time to the chat date and time
    - welcome message is now displayed in the middle of the screen
    - add `welcomeMessageTextColor` key to customize the text Color of the welcome message
    - make the default colors compatible with the dark mode
    - remove `rc_send_attachment_img` localization key

## Dimelo Android 1.9.1 (September 21th, 2020) ##
- Minor: Bump `targetSdkVersion` to **API 29** (was API 26). RD-14789

## Dimelo Android 1.9.0 (January 20th, 2020) ##
- Improvement: add ([`Localization.md`](Localization.md)) to describe how to customize strings in Engage Digital Messaging SDK. RD-11671
- Improvement: prefix all the strings key (in `res/values/strings.xml`) with `rc_` and display a warning if the not-prefixed key is used. RD-11671
- Improvement: add `rc_attachment_size_label_megabyte_unit` and `rc_attachment_size_label_kilobyte_unit` keys to customize the size unit of the attachment. RD-11671
-  Feature: allow to initialize the `Dimelo` instance using a hostname RD-10821:
  	*  add `initializeWithApiKeyAndHostName(String apiKey, String hostName, DimeloListener dimeloListener)`  method to configure Dimelo with an api key and a host name.
  	*  add `initializeWithApiSecretAndHostName(String apiSecret, String hostName, DimeloListener dimeloListener)`  method to configure Dimelo with an api secret and a host name.
- BREAKING CHANGE: remove deprecated methods related to welcome message (`setWelcomeMessage(String welcomeMessage)` and `getWelcomeMessage()`). The welcome messages are retrieved from the Engage Digital source configuration thus these methods being removed. RD-11736
- Fix: content of "To" is incorrect when sharing file with Gmail. RD-11559

## Dimelo Android 1.8.0 (October 7th, 2019) ##
- BREAKING CHANGE: Bump minimal supported Android version (`minSdkVersion`) to **API 16** (was API 15). RD-10562
- Improvement: Upgrade google place API from `com.google.android.gms:play-services-places:16.0.0` to `com.google.android.libraries.places:places-compat:1.1.0`. RD-10562
- Improvement: Remove duplicated attachment preview screen when sending location or an image from the gallery. RD-10946
- Fix: attachment weren't clickable anymore after opening another non-image attachment
- Improvement: add prefix to the layouts file name to prevent conflicts

## Dimelo Android 1.7.2 (June 18th, 2019) ##
- Fix: gallery thumbnails were shrinking when opening attachment menu multiple times. RD-10508
- Fix: namespace Picasso library to avoid conflicts (#49). RD-10583

## Dimelo Android 1.7.1 (January 15th, 2019) ##
- Improvement: Bump GMS dependency from v11.0.4 to v16.0.0 (#43). RD-10063
- Fix: apache no class def found error on Android 9 (API 28) (#44) RD-10113
- Fix: message deeplink parsing was sometimes crashing app on low-performance devices. RD-10064
- Feature: now display an error icon alongside the message when the sending request failed and allow to customize its tint color using the `errorIconColor` option. RD-9309
- Improvement: disable network calls to Dimelo mobile API when source is disabled. RD-9139

## Dimelo Android 1.7.0 (October 31th, 2018) ##
- BREAKING CHANGE: new mandatory domain name configuration (first part of your Dimelo Digital URL: **domain-name**.engagement.dimelo.com) RD-9197:
  * `setApiSecret(String apiSecret)` is now deprecated in favor of `initWithApiSecret(String secret, String domainName, DimeloListener dimeloListener)`.
  * `setApiKey(String apiKey)` is now deprecated in favor of `initWithApiKey(String apiKey, String domainName, DimeloListener dimeloListener)`.
  * `setHostname(String  hostname)` is not available anymore.
- Improvement: Dimelo instance setup no longer require to be run in the main thread when receiving notifications. RD-9934
- Feature: add local draft saving for unsent text messages. RD-9024
- Fix: dimelo notifications crash on android jelly bean (android api 15). RD-9850
- Improvement: log a warning when an invalid key is used for installations or users extra values. RD-9765

## Dimelo Android 1.6.9 (August 14th, 2018) ##
- Improvement: image upload resilience to low memory devices (#37). RD-9216
- Improvement: make dimelo notifications processing more robust
- Fix: prevent sending empty body in send message request. RD-9226
- Improvement: limit input text height to 20% of screen height when text is entered
- Feature: namespace Glide library to avoid conflicts. RD-9629
- Feature: add deep links support. RD-9425

## Dimelo Android 1.6.8 (April 19th, 2018) ##
- Feature: add navigationBarTitleFont to customize the navigationBar title font (minimum android SDK version equal to 18 when using Dimelo as Fragment). RD-9357
- Fix: mapView crash on landscape mode when trying to select location. RD-9337
- Fix: crash when taking photo from camera or gallery then rotating the screen. RD-9339
- Fix: prevent multiple tap on attachements from opening multiple zoom views. RD-9268

## Dimelo Android 1.6.7 (February 23th, 2018) ##
- Improvement: change Volley request to support retry number and back off multiplier. RD-8987
- Fix: notifications are not working with Firebase for API >= 26. RD-9183

## Dimelo Android 1.6.6 (February 9th, 2018) ##
- Fix: nullPointException when sending message using the inline reply and the application is killed. RD-9082
- Fix: empty content when opening chat from notification and the application is killed
- Feature: add navigationBarTitleColor and navigationBarItemTintColor to customize the navigationBar title and the navigationBarItem tint color. RD-9095
- Fix: standard Activity crash on landscape mode. RD-9097

## Dimelo Android 1.6.5 (December 4th, 2017) ##
- Fix: nullPointException when saving instance state (#31). RD-8976
- Fix: refresh chat view on main thread

## Dimelo Android 1.6.4 (November 7th, 2017) ##
- Feature: add onOpen and onClose callback
- Feature: Support any kind of attachment for agent only
- Improvement: Add the interactive push notification with direct reply
- Feature: Add new API to send a customer message

## Dimelo Android 1.6.3 (September 18th, 2017) ##
- Fix: Improve image quality (attachment + thumbnail)
- Fix: Add the JWT payload parsing in order to fill the attributes (mUserIdentifier, mUserName and mAuthenticationInfo)
- Fix: Add attachmentIcon customization option
- Fix: Remove scroll down animation when the message list is loaded for the first time

## Dimelo Android 1.6.2 (August 9th, 2017) ##
- Fix: check if camera permission is present in the manifest before display or hide the camera button
- Fix: prevent some push notifications to be lost if the SDK is not properly initialized (no userIdentifier)

## Dimelo Android 1.6.1 (July 25th, 2017) ##
- Fix: crash when displaying messages with attached photo

## Dimelo Android 1.6.0 (July 19th, 2017) ##
- Improvement: add GIF support
- Fix: add camera files support for Android 7.0 (API 24) and above (#20)
- Fix: remove android:label in SDK manifest and app_name/sdk_name values in strings.xml

## Dimelo Android 1.5.3 (February 6th, 2017) ##
- Fix: nullPointException when stoping the app if attachments are disabled (#18)

## Dimelo Android 1.5.2 (January 31st, 2017) ##
- Fix: library attachment button was not clickable
- Improvement: better handling of runtime permissions for attachment. Please don't forget to specify appropriate permissions in your AndroidManifest.
- Improvement: check that camera device is available, otherwise disable camera attachment
- Fix: possible blinking effect of welcome message on multi-user installations

## Dimelo Android 1.5.1 (January 30th, 2017) ##
- Feature: Add feature asked in #17. You can now specify which activity should be launched when a notification has been clicked thanks to the new `consumeReceivedRemoteNotification` method:

```java
public static boolean consumeReceivedRemoteNotification(@NonNull Context context, @NonNull Bundle payload, @Nullable NotificationDisplayer notifDisplayer, @Nullable Class<?> activity);
```

## Dimelo Android 1.5.0 (January 18th, 2017) ##
- Feature: Add ability to disable attachments. It is now possible to disable the ability to send images and/or photos and/or location.
- Improvement: GMS is now an optional library. By default, the library is provided, but it can be excluded: the application will still work but location attachments will be disabled. Note that disabling location will not remove GMS from the dependencies.
- Fix: issue #13. Provide translation for the app_name provided in our strings.xml
- Fix: issue #14. Fix default color of the button in disable state
- Feature: related to issue #14. Add ability to customize the color of the send button is enabled state (see setSendButtonEnabledcolor)
- Fix: issue #15. setDeviceToken can now be run in a background thread without throwing exception.
- Fix: Rollback installationId fix of v1.4.2 and provide another instead. Now check the userIdenfier: notifications with a userIdentifier different from the current one will be skipped.

## Dimelo Android 1.4.4 (January 9th, 2017) ##
- Improvement: Reduce .aar size to ~320KB by removing dependency to RenderScript. Client apps do not need to include RenderScript anymore.

## Dimelo Android 1.4.3 (December 19th, 2016) ##
- Fix: Patch blinking effect of the welcome message at application startup.

## Dimelo Android 1.4.2 (December 9th, 2016) ##
- Change: Bump GMS dependency from v8.1.0 to v9.8.0.
- Fix: Check installationId when receiving a new notification. Only process notifications where the notificationId matches the current installationId.

## Dimelo Android 1.4.1 (November 28th, 2016) ##
- Fix: In the case no welcome message has been defined, the application was displaying a message containg the string "null". This is now fixed.

## Dimelo Android 1.4.0 (November 24th, 2016) ##
- Feature: Add ability to define a welcome message which is automatically displayed when a conversation is empty.
- Improvements: Some performance, security and accessibility improvements.

## Dimelo Android 1.3.1 (November 3rd, 2016) ##
- Fix: Do not strip whitespaces and newlines from JWT dictionary

## Dimelo Android 1.3.0 (October 19th, 2016) ##
- Feature: Add the UnreadCount feature to poll the number of unread messages.

## Dimelo Android 1.2.3 (October 11th, 2016) ##
- Feature: Allow customization of text size.

## Dimelo Android 1.2.2.2 (September 09th, 2016) ##
- Fix: Messages are now always correctly received and sent after internet recovery.
- Fix: Activity mode is now compatible with host applications that are not using AppCompat (Fixed crash when uploading an attachment)

## Dimelo Android 1.2.2.1 (August 25th, 2016) ##
- Fix: Messages are now correctly received and sent after internet recovery (when starting offline).

## Dimelo Android 1.2.2 (July 11th, 2016) ##
- Fix: Upgrade gradle to fix potential issues with native libraries.

## Dimelo Android 1.2.1 (July 5th, 2016) ##
- Fix: "Share" feature (removed hard-coded reference to autorithy `com.dimelo.fileprovider`).
- Fix: Use custom inherited FileProvider class to prevent conflicts.


## Dimelo Android 1.2.0 (May 19th, 2016) ##
- Feature: Remove local cache file
- Feature: Allow customization of attachments icon
- Fix: Compatibility with a wider range of Android Support libraries

## Dimelo Android 1.1.4 (May 19th, 2016) ##
- Fix: button geometry with Android API 19
- FIx: layout size calculation with Android Support Library > 23.3.0

## Dimelo Android 1.1.3 (May 11th, 2016) ##
- Fix: compatibility with Android Support Library > 23.1

## Dimelo Android 1.1.2 (April 14th, 2016) ##
- Feature: It is now possible to customize text message and attachments background with different bubbles
- Feature: It is now possible to customize the color the send message arrow when disabled (no text & no attachment selected)
- Fix: Fixed crash which occured when the SDK was used without `com.google.android.geo.API_KEY`

## Dimelo Android 1.1.1 (January 13th, 2016) ##
- Fix: Fixed crash when calling setUserIdentifier or setJwt after first chat setup.

## Dimelo Android 1.1.0 (December 18th, 2015) ##
- Feature: Added support for image and location attachments.


## Dimelo Android 1.0.0 (July 7th, 2015) ##
- Feature: First official release supporting Dimelo Mobile protocol but limited to text
  interaction.
