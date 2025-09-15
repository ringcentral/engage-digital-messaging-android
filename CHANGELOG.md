# Engage Digital Messaging - Android master #

## Engage Digital Messaging - Android 3.3.9 (September 15th, 2025) ##
- Feature: show a typing animation when conversation is handled by a bot. RD-32157

## Engage Digital Messaging - Android 3.3.8 (August 12th, 2025) ##
- Improvement: add visual clue to show that thumbs up/down button has been pressed. RD-36721

## Engage Digital Messaging - Android 3.3.7 (July 11th, 2025) ##
- Fix: prevent the date from disappearing when scrolling. RD-33320

## Engage Digital Messaging - Android 3.3.6 (July 3rd, 2025) ##
- Fix: rating a bot message with a thumbs up was mistakenly showing a thumbs down after providing the feedback. RD-36013

## Engage Digital Messaging - Android 3.3.5 (June 25th, 2025) ##
- Feature: display thumbs up/down choice and allow user to send feedback when rating a message. RD-34095

## Engage Digital Messaging - Android 3.3.4 (May 30th, 2025) ##
- Improvement: replace Trebuchet bold font with Roboto bold. RD-33273

## Engage Digital Messaging - Android 3.3.3 (April 29th, 2025) ##
- Fix: opening and closing the keyboard repeatedly makes the keyboard intermittently overlap on messages. RD-21615
- Fix: pre-chat form configuration lag can prevent the user from entering the chat. RD-33252

## Engage Digital Messaging - Android 3.3.2 (April 18th, 2025) ##
- Feature: allow chatbot to use a different avatar than the channel. RD-32238

## Engage Digital Messaging - Android 3.3.1 (April 10th, 2025) ##
- Fix: having no pre-chat form configured on the channel was causing the SDK to open a blank webview. RD-33109

## Engage Digital Messaging - Android 3.3.0 (March 18th, 2025) ##
- Feature: add support for messaging pre-chat forms. RD-31550
- Improvement: in some cases opening the chat via a push notification was showing an empty conversation. RD-32770

## Engage Digital Messaging - Android 3.2.11 (March 12th, 2025) ##
- Fix: in some rare cases WebView could be displayed with the wrong height on some devices. RD-26103
- Improvement: subscribe to notification channel when initializing the Dimelo instance. RD-32333
- Fix: in some cases a nullPointerException was thrown when displaying the avatar. RD-32539

## Engage Digital Messaging - Android 3.2.10 (January 27th, 2025) ##
- Fix: in some cases the threads loader indicator visibility was being changed outside of the UI thread. RD-32438

## Engage Digital Messaging - Android 3.2.9 (December 23th, 2024) ##
- Fix: the `Dimelo.getJwtDictionary()` was including empty data that prevented the server from correctly authenticating the user when accessing the chat through a notification. RD-32293

## Engage Digital Messaging - Android 3.2.8 (November 29th, 2024) ##
- Fix: revert `Fix: in some cases quick reply wasn't disappearing immediately after the thread was closed. RD-23974` because of a bug in the quick replies display

## Engage Digital Messaging - Android 3.2.7 (November 28th, 2024) ##
- Fix: invalidate cache when user identifier changes. RD-32046

## Engage Digital Messaging - Android 3.2.6 (November 22th, 2024) ##
- Improvement: remove the horizontal gallery and use the native Android photo picker. RD-31553:
    - The `READ_MEDIA_IMAGES` permission is not needed anymore.
    - The `READ_MEDIA_VIDEOS` permission is not needed anymore.

## Engage Digital Messaging - Android 3.2.5 (November 20th, 2024) ##
- Feature: allow to disable the text input via API. RD-30696

## Engage Digital Messaging - Android 3.2.4 (September 25th, 2024) ##
- Fix: in some cases quick reply wasn't disappearing immediately after the thread was closed. RD-23974
- Fix: location messages can disappear when scrolling while internet is off. RD-30225
- Improvement: add RTL support for structured messages. RD-30711

## Engage Digital Messaging - Android 3.2.3 (September 11th, 2024) ##
- Improvement: the chat does not open automatically when all threads are closed when integrated as an activity. RD-30443

## Engage Digital Messaging - Android 3.2.2 (August 21th, 2024) ##
- Feature: extend support for identity fields. RD-29583:
    - Add the `setCompany` method. RD-29799
    - Add the `setEmail` method. RD-29800
    - Add the `setFirstname` method. RD-29801
    - Add the `setLastname` method. RD-29802
    - Add the `setHomePhone` method. RD-30548
    - Add the `setMobilePhone` method. RD-30550

## Engage Digital Messaging - Android 3.2.1 (August 1st, 2024) ##
- Improvement: add a customizable informative text below the last message when the thread is closed. RD-16691
- Fix: the chat fails to display when integrated as an activity (introduced in v3.2.0). RD-30334

## Engage Digital Messaging - Android 3.2.0 (July 8th, 2024) ##
- Feature: allow to initialize the SDK using the Engage Messaging channel's token. RD-28848
*  add `initializeWithToken(String token, String hostname, String jwtKeyId, String jwtSecret, DimeloListener dimeloListener)` (for adhoc JWT signing).
*  add `initializeWithToken(String token, String hostname, DimeloListener dimeloListener)` (for remote JWT signing).

## Engage Digital Messaging - Android 3.1.1 (June 21th, 2024) ##
- Fix: previously sent locations are not fully displayed if connection was lost. RD-23649
- Fix: unread messages count badge disappears after screen rotation. RD-23248
- Improvement: `consumeReceivedRemoteNotification` will check the notification payload before initializing the SDK. RD-29984
- Fix: application crashed when receiving a message while the button to scroll to the end of conversation was visible. RD-29244
- Improvement: add `setDefaultLanguage(Locale locale)` to set the application language. RD-29788
- Fix: prevent empty thread from being displayed in threads list. RD-29706
- Improvement: add the ability to customize the toolbar title color and the back button color. RD-29816
- Fix: the loading popup was shown endlessly when selecting some type of files. RD-29453

## Engage Digital Messaging - Android 3.1.0 (April 23th, 2024) ##
- Feature: add support for FCM HTTP v1 API. RD-29454

## Engage Digital Messaging - Android 3.0.4 (March 14th, 2024) ##
- Feature: add support for thumbs up/down rating on messages generated by Dialogflow virtual agent. RD-28808

## Engage Digital Messaging - Android 3.0.3 (March 4th, 2024) ##
- Fix: the button to scroll to the bottom of the conversation's position wasn't correctly updated when the text input was hidden when closing a thread. RD-28894
- Fix: opening the attachment menu was making the text input disappear (introduced in v3.0.2). RD-29148
- Fix: the button to scroll to the bottom of the conversation was still displayed after the auto-scroll when sending/receiving a new message. RD-28907
- Improvement: removed the blank space on top and at the bottom on the conversation. RD-18441
- Improvement: calling `sendMessage(String message)` will now trigger the `dimeloChatDidSendMessage()` callback. RD-28914

## Engage Digital Messaging - Android 3.0.2 (January 15th, 2024) ##
- Feature: add a button to scroll to the bottom of the conversation (disabled by default). RD-27768
- Fix: a nullPointerException was thrown when closing the app in the middle of a screen rotation. RD-28575
- Fix: in some cases the text input wasn't hidden when the context menu was open. RD-27844
- Improvement: update the notification badge with the number of unread messages. RD-18575
- Fix: quick replies sent with `disable_text_input` option are not correctly displayed for fragment integration when only threading are disabled. RD-27283
- Fix: in some rare cases when threads are enabled, default customization instance was causing the application to crash. RD-27923

## Engage Digital Messaging - Android 3.0.1 (October 5th, 2023) ##
- Feature: add support for message deletion. RD-27258

## Engage Digital Messaging - Android 3.0.0 (August 30th, 2023) ##
- BREAKING CHANGE: Migrate SDK to AndroidX. RD-25847 RD-26687
- Minor: bump `minSdk` to **API 19** (was **API 16**). RD-25847
- Fix: in some cases a nullPointerException was thrown when using webview (introduced in v2.5.2). RD-27154
- Fix: in some cases rotating the device while sending a picture was causing the chat to be empty. RD-24448

## Engage Digital Messaging - Android 2.5.2 (April 17th, 2023) ##
- Fix: prevent a crash when clicking on a retry button just after internet connection has been restored. RD-26101
- Fix: fix deprecated methods for push notification on Android 6+. RD-23388
- Fix: messages list was sometimes empty when rotating the device while internet connection was off. RD-23445
- Fix: in some cases messages couldn't be sent after disabling and re-enabling internet connection. RD-23228
- Fix: in some rare cases fullsize WebView can be displayed with the wrong size on some devices. RD-22557
- Fix: some pictures were displayed with a wrong orientation. RD-22142
- Fix: in some cases rotating while in the Android gallery was causing the horizontal gallery to be empty. RD-25033
- Fix: in some cases rotating while in the Android gallery was causing the attachment buttons to be disabled. RD-25035
- Fix: Prevent the horizontal gallery from being empty after sending an attachment. RD-24297
- Fix: prevent going back to the threads list when there's no thread created yet. RD-23127

## Engage Digital Messaging - Android 2.5.1 (January 17th, 2023) ##
- Fix: some files were sent with an incorrect Content-Type header to the server. RD-24441
- Fix: use new API 33 permissions for media access when running on an Android 13+ device. RD-24668
- Feature: support auto open of richlink survey webview link. RD-24458
- Minor: bump `targetSdkVersion` to **API 33** (was **API 31**). RD-24685
- Fix: ask for push notification permission for device running on Android 13+. RD-24685
- Improvement: keep the carousel horizontal scroll position in memory even after scrolling into the conversation. RD-21103

## Engage Digital Messaging - Android 2.5.0 (December 9th, 2022) ##
- Feature: add support for videos in the gallery selection. RD-23883
- Feature: add the ability to send document files. RD-23884

## Engage Digital Messaging - Android 2.4.4 (October 28th, 2022) ##
- Fix: prevent NullPointerException when clicking on a link without having a DimeloListener implemented. RD-23876

## Engage Digital Messaging - Android 2.4.3 (October 18th, 2022) ##
- Fix: in some cases links were not clickable anymore when coming back to the chat. RD-24065
- Fix: auto scroll to the bottom when receiving a quick replies structured message. RD-20309
- Fix: structured messages reply items couldn't be used before the thread status was fetched. RD-23256
- Improvement: in some cases the conversation was disappearing as soon as an agent response was received on device running on Android 9+. RD-23145

## Engage Digital Messaging - Android 2.4.2 (August 18th, 2022) ##
- Fix: links in message weren't clickable without reloading the application on phone using Android 10 and lower. RD-23148

## Engage Digital Messaging - Android 2.4.1 (August 9th, 2022) ##
- BREAKING CHANGE: change the `rcShouldDelegateUrlOpening` method signature in `DimeloListener` from `rcShouldDelegateUrlOpening(URL url)` to `rcShouldDelegateUrlOpening(URI uri)` to allow usage of Uri with custom scheme. RD-22996
- Fix: in some conditions the Switch to Video icon was still slightly visible after being hidden. RD-23117
- Fix: Switch to Video icon was displayed regardless of the channel configuration. RD-23097

## Engage Digital Messaging - Android 2.4.0 (August 3rd, 2022) ##
- Bug introduced (please use `v2.4.1` instead): Switch to Video icon was displayed regardless of the channel configuration. RD-23097
- Feature: add support for Switch to Video. RD-22097

## Engage Digital Messaging - Android 2.3.4 (May 31th, 2022) ##
- Bug introduced: structured messages reply items couldn't be used before the thread status was fetched. Fixed in `v2.4.3`. RD-23256
- Bug introduced: links in message weren't clickable without reloading the application on phone using Android 10 and lower. Fixed in `v2.4.2`. RD-23148
- Feature: add the `openWebView(URL url, RC_WEB_VIEW_SIZE height)` method to allow to manually open a WebView within the chat. RD-21672
- Feature: add the `rcShouldDelegateUrlOpening(URL url)` method to `DimeloListener` to control whether the Engage Messaging SDK should open a URL or not. RD-21672
- Fix: Remove highlight from the attachment icon when gallery preview is closed because of a swipe. RD-19559
- Fix: text input flickers when thread is locked and conversation is scrolled from top to bottom. RD-21508
- Fix: Prevent template/carousel reply usage while being in a locked thread when threads are enabled and leave the other url clickable. RD-18412
- Fix: full-sized WebView has an inconsistent size across various devices. RD-21712

## Engage Digital Messaging - Android 2.3.3 (April 6th, 2022) ##
- Improvement: automatically close the keyboard before opening a WebView. RD-21729
- Fix: webview opened through an image in a structured message header was causing the application to crash when it was closed using the close button or by clicking outside the webview. RD-21772
- Feature: support the company message view in the threads list. RD-16265

## Engage Digital Messaging - Android 2.3.2 (March 31th, 2022) ##
- Fix: structured message items cannot be used anymore after using a "reply" item. RD-21705
- Improvement: localize the cancel button text when asking for permissions. RD-19410

## Engage Digital Messaging - Android 2.3.1 (March 18th, 2022) ##
- Bug introduced: structured message items cannot be used anymore after using a "reply" item. Fixed in `v2.3.2`. RD-21705
- Fix: prevent template/carousel "reply" items usage while being in a locked thread. RD-18412
- Fix: customization of openGalleryIcon, attachmentIcon, backToAllChatsImage and lockedThreadImage were broken while having threads enabled. RD-21090
- Fix: Prevent the input zone from moving when asking for permissions. RD-19164
- Fix: prevent quick reply usage while being in a locked thread when threads are enabled. RD-18410
- Improvement: prevent opening multiple webViews/browser pages when opening a URL through a structured message. RD-20877
- Feature: url sent in a structured message (richlink, carousel or template) can now be displayed as an embedded WebView. RD-20877
    - The WebView is opened in full height mode when `target` is equal to `current`

## Engage Digital Messaging - Android 2.3.0 (January 21st, 2022) ##
- Feature: add integration with [Engage Digital Messaging Maps SDK](https://github.com/ringcentral/engage-digital-messaging-android-location). RD-19661
- Minor: Bump Google support libraries to `v28.0.0`. RD-16301

## Engage Digital Messaging - Android 2.2.2 (October 20th, 2021) ##
- Minor: Bump `targetSdkVersion` to **API 31** (was **API 30**). RD-19785
- Fix: Add `PendingIntent.FLAG_MUTABLE` to prevent a crash when receiving an interactive push notification on application targeting Android 12 and higher. RD-19785
- Fix: Add `PendingIntent.FLAG_IMMUTABLE` to prevent a crash when receiving a push notification on application targeting Android 12 and higher. RD-19794
- Fix: Add `android:exported="false"` to Manifest to resolve the incompatibility with application targeting Android 12 and higher. RD-19794

## Engage Digital Messaging - Android 2.2.1 (September 30th, 2021) ##
- Fix: Prevent tapping on template and carousel item reply when the input text is disabled. RD-18408
- Fix: Back button now closes the gallery if opened when threading is enabled. RD-19183

## Engage Digital Messaging - Android 2.2.0 (September 15th, 2021) ##
- Improvement: remove location message and replace it with an url message in the chat view. RD-18952
- Improvement: remove deprecated dependency `com.google.android.gms:play-services-location:16.0.0`. RD-18952
- Feature: Add support for Huawei push notifications (HMS). RD-18475 RD-18476 RD-18477 RD-18885

## Engage Digital Messaging - Android 2.1.2 (September 1st, 2021) ##
- Minor: Bump `targetSdkVersion` to **API 30** (was API 29). RD-16629

## Engage Digital Messaging - Android 2.1.1 (August 17th, 2021) ##
- Improvement: Change the disabled color of the send/attachment button. RD-18578
- Improvement: Add the ability to zoom in/out when opening pictures. RD-12597
- Improvement: Send the file extension with the filename when sending an attachment. RD-16647
- Fix: Update media "Authorization required" alert to redirect to the application setting. RD-17562

## Engage Digital Messaging - Android 2.1.0 (July 12th, 2021) ##
- BREAKING CHANGE: When integrating the SDK as a fragment:
    - The `newChatFragment()` method has been removed in favor of the new `newRcFragment()` method. RD-16261
    - The `Chat` type has been removed in favor of the new `RcFragment` type. RD-16261
    - The `newRcFragment()` method will either instantiate the chat or the conversations list based on the threading activation/deactivation. RD-16261
    - To customize the conversations list or the chat, use `RcFragment.Customization` (`Chat.Customization` will no longer be available). RD-14564
- BREAKING CHANGE: When integrating the SDK as an activity:
    - The `openChatActivity()` method has been removed in favor of the new `openRcActivity()` method. RD-16261
    - The `openChatActivityNoActionBar()` method has been removed in favor of the new `openRcActivityNoActionBar()` method. RD-16261
    - `setOnActivitySetupAppearenceListener.onSetupAppearance` now expects a `RcFragment.Customization` to be passed as argument (it was previously expecting a `Chat.Customization`). RD-14564
- Feature: add threading support. RD-16261:
    - Add `enableThreads` flag to enable or disable the threading. RD-16275
    - Add threads-related customization keys ([listed in Customization.md](Customization.md)). RD-14564
    - Set a context_data `identity_initiated_thread: true` when clicking on the "new conversation" button. RD-16234
    - Hide the "new conversation" button based on the "Allow multiple conversations in parallel" ED configuration with a maximum of three parallel open threads. RD-16248
    - Handle server parallel threads creation anti-flood error. RD-16245
    - Support local draft by thread. RD-16279

## Engage Digital Messaging - Android 2.0.6 (April 19th, 2021) ##
- Fix: Cannot send a photo from recent photos gallery on android 10 (API 29). RD-17666

## Engage Digital Messaging - Android 2.0.5 (April 8th, 2021) ##
- Improvement: Add `openGalleryBackgroundColor`, `openGalleryIconColor` keys and `setOpenGalleryIcon()` method to customize the open gallery button. RD-17275
- Minor BREAKING CHANGE: `openGalleryBackgroundColor` no longer uses the theme color. RD-17275

## Engage Digital Messaging - Android 2.0.4 (April 6th, 2021) ##
- Fix: Handle structured messages sent from system. RD-17116
- Fix the gray screen when opening camera on android 10 (API 29). RD-13580
- Fix: prevent automatic generation of a gray image in recent photo and gallery app after taking a photo or canceling it on android 10+ (API 29+). RD-17442

## Engage Digital Messaging - Android 2.0.3 (March 1st, 2021) ##
- Improvement: disable `glide` modules for our namespaced singleton. RD-16974

## Engage Digital Messaging - Android 2.0.2 (January 25th, 2021) ##
- Improvement: drop `picasso` dependency. RD-16311 RD-16345

## Engage Digital Messaging - Android 2.0.1 (December 17th, 2020) ##
- Fix: some words were wrongly underlined when mixed with deep links containing \n or \r. RD-12675
- Improvement: move the cursor to the last position in the input text after screen rotation or resuming the chat. RD-15714
- Improvement: keep the keyboard draft when rotating the screen on a fragment. RD-15714

## Engage Digital Messaging - Android 2.0.0 (December 1st, 2020) ##
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

## Engage Digital Messaging - Android 1.9.1 (September 21th, 2020) ##
- Minor: Bump `targetSdkVersion` to **API 29** (was API 26). RD-14789

## Engage Digital Messaging - Android 1.9.0 (January 20th, 2020) ##
- Improvement: add ([`Localization.md`](Localization.md)) to describe how to customize strings in Engage Digital Messaging SDK. RD-11671
- Improvement: prefix all the strings key (in `res/values/strings.xml`) with `rc_` and display a warning if the not-prefixed key is used. RD-11671
- Improvement: add `rc_attachment_size_label_megabyte_unit` and `rc_attachment_size_label_kilobyte_unit` keys to customize the size unit of the attachment. RD-11671
-  Feature: allow to initialize the `Dimelo` instance using a hostname RD-10821:
  	*  add `initializeWithApiKeyAndHostName(String apiKey, String hostName, DimeloListener dimeloListener)`  method to configure Dimelo with an api key and a host name.
  	*  add `initializeWithApiSecretAndHostName(String apiSecret, String hostName, DimeloListener dimeloListener)`  method to configure Dimelo with an api secret and a host name.
- BREAKING CHANGE: remove deprecated methods related to welcome message (`setWelcomeMessage(String welcomeMessage)` and `getWelcomeMessage()`). The welcome messages are retrieved from the Engage Digital source configuration thus these methods being removed. RD-11736
- Fix: content of "To" is incorrect when sharing file with Gmail. RD-11559

## Engage Digital Messaging - Android 1.8.0 (October 7th, 2019) ##
- BREAKING CHANGE: Bump minimal supported Android version (`minSdkVersion`) to **API 16** (was API 15). RD-10562
- Improvement: Upgrade google place API from `com.google.android.gms:play-services-places:16.0.0` to `com.google.android.libraries.places:places-compat:1.1.0`. RD-10562
- Improvement: Remove duplicated attachment preview screen when sending location or an image from the gallery. RD-10946
- Fix: attachment weren't clickable anymore after opening another non-image attachment
- Improvement: add prefix to the layouts file name to prevent conflicts

## Engage Digital Messaging - Android 1.7.2 (June 18th, 2019) ##
- Fix: gallery thumbnails were shrinking when opening attachment menu multiple times. RD-10508
- Fix: namespace Picasso library to avoid conflicts (#49). RD-10583

## Engage Digital Messaging - Android 1.7.1 (January 15th, 2019) ##
- Improvement: Bump GMS dependency from v11.0.4 to v16.0.0 (#43). RD-10063
- Fix: apache no class def found error on Android 9 (API 28) (#44) RD-10113
- Fix: message deeplink parsing was sometimes crashing app on low-performance devices. RD-10064
- Feature: now display an error icon alongside the message when the sending request failed and allow to customize its tint color using the `errorIconColor` option. RD-9309
- Improvement: disable network calls to Dimelo mobile API when source is disabled. RD-9139

## Engage Digital Messaging - Android 1.7.0 (October 31th, 2018) ##
- BREAKING CHANGE: new mandatory domain name configuration (first part of your Dimelo Digital URL: **domain-name**.engagement.dimelo.com) RD-9197:
  * `setApiSecret(String apiSecret)` is now deprecated in favor of `initWithApiSecret(String secret, String domainName, DimeloListener dimeloListener)`.
  * `setApiKey(String apiKey)` is now deprecated in favor of `initWithApiKey(String apiKey, String domainName, DimeloListener dimeloListener)`.
  * `setHostname(String  hostname)` is not available anymore.
- Improvement: Dimelo instance setup no longer require to be run in the main thread when receiving notifications. RD-9934
- Feature: add local draft saving for unsent text messages. RD-9024
- Fix: dimelo notifications crash on android jelly bean (android api 15). RD-9850
- Improvement: log a warning when an invalid key is used for installations or users extra values. RD-9765

## Engage Digital Messaging - Android 1.6.9 (August 14th, 2018) ##
- Improvement: image upload resilience to low memory devices (#37). RD-9216
- Improvement: make dimelo notifications processing more robust
- Fix: prevent sending empty body in send message request. RD-9226
- Improvement: limit input text height to 20% of screen height when text is entered
- Feature: namespace Glide library to avoid conflicts. RD-9629
- Feature: add deep links support. RD-9425

## Engage Digital Messaging - Android 1.6.8 (April 19th, 2018) ##
- Feature: add navigationBarTitleFont to customize the navigationBar title font (minimum android SDK version equal to 18 when using Dimelo as Fragment). RD-9357
- Fix: mapView crash on landscape mode when trying to select location. RD-9337
- Fix: crash when taking photo from camera or gallery then rotating the screen. RD-9339
- Fix: prevent multiple tap on attachements from opening multiple zoom views. RD-9268

## Engage Digital Messaging - Android 1.6.7 (February 23th, 2018) ##
- Improvement: change Volley request to support retry number and back off multiplier. RD-8987
- Fix: notifications are not working with Firebase for API >= 26. RD-9183

## Engage Digital Messaging - Android 1.6.6 (February 9th, 2018) ##
- Fix: nullPointException when sending message using the inline reply and the application is killed. RD-9082
- Fix: empty content when opening chat from notification and the application is killed
- Feature: add navigationBarTitleColor and navigationBarItemTintColor to customize the navigationBar title and the navigationBarItem tint color. RD-9095
- Fix: standard Activity crash on landscape mode. RD-9097

## Engage Digital Messaging - Android 1.6.5 (December 4th, 2017) ##
- Fix: nullPointException when saving instance state (#31). RD-8976
- Fix: refresh chat view on main thread

## Engage Digital Messaging - Android 1.6.4 (November 7th, 2017) ##
- Feature: add onOpen and onClose callback
- Feature: Support any kind of attachment for agent only
- Improvement: Add the interactive push notification with direct reply
- Feature: Add new API to send a customer message

## Engage Digital Messaging - Android 1.6.3 (September 18th, 2017) ##
- Fix: Improve image quality (attachment + thumbnail)
- Fix: Add the JWT payload parsing in order to fill the attributes (mUserIdentifier, mUserName and mAuthenticationInfo)
- Fix: Add attachmentIcon customization option
- Fix: Remove scroll down animation when the message list is loaded for the first time

## Engage Digital Messaging - Android 1.6.2 (August 9th, 2017) ##
- Fix: check if camera permission is present in the manifest before display or hide the camera button
- Fix: prevent some push notifications to be lost if the SDK is not properly initialized (no userIdentifier)

## Engage Digital Messaging - Android 1.6.1 (July 25th, 2017) ##
- Fix: crash when displaying messages with attached photo

## Engage Digital Messaging - Android 1.6.0 (July 19th, 2017) ##
- Improvement: add GIF support
- Fix: add camera files support for Android 7.0 (API 24) and above (#20)
- Fix: remove android:label in SDK manifest and app_name/sdk_name values in strings.xml

## Engage Digital Messaging - Android 1.5.3 (February 6th, 2017) ##
- Fix: nullPointException when stoping the app if attachments are disabled (#18)

## Engage Digital Messaging - Android 1.5.2 (January 31st, 2017) ##
- Fix: library attachment button was not clickable
- Improvement: better handling of runtime permissions for attachment. Please don't forget to specify appropriate permissions in your AndroidManifest.
- Improvement: check that camera device is available, otherwise disable camera attachment
- Fix: possible blinking effect of welcome message on multi-user installations

## Engage Digital Messaging - Android 1.5.1 (January 30th, 2017) ##
- Feature: Add feature asked in #17. You can now specify which activity should be launched when a notification has been clicked thanks to the new `consumeReceivedRemoteNotification` method:

```java
public static boolean consumeReceivedRemoteNotification(@NonNull Context context, @NonNull Bundle payload, @Nullable NotificationDisplayer notifDisplayer, @Nullable Class<?> activity);
```

## Engage Digital Messaging - Android 1.5.0 (January 18th, 2017) ##
- Feature: Add ability to disable attachments. It is now possible to disable the ability to send images and/or photos and/or location.
- Improvement: GMS is now an optional library. By default, the library is provided, but it can be excluded: the application will still work but location attachments will be disabled. Note that disabling location will not remove GMS from the dependencies.
- Fix: issue #13. Provide translation for the app_name provided in our strings.xml
- Fix: issue #14. Fix default color of the button in disable state
- Feature: related to issue #14. Add ability to customize the color of the send button is enabled state (see setSendButtonEnabledcolor)
- Fix: issue #15. setDeviceToken can now be run in a background thread without throwing exception.
- Fix: Rollback installationId fix of v1.4.2 and provide another instead. Now check the userIdenfier: notifications with a userIdentifier different from the current one will be skipped.

## Engage Digital Messaging - Android 1.4.4 (January 9th, 2017) ##
- Improvement: Reduce .aar size to ~320KB by removing dependency to RenderScript. Client apps do not need to include RenderScript anymore.

## Engage Digital Messaging - Android 1.4.3 (December 19th, 2016) ##
- Fix: Patch blinking effect of the welcome message at application startup.

## Engage Digital Messaging - Android 1.4.2 (December 9th, 2016) ##
- Change: Bump GMS dependency from v8.1.0 to v9.8.0.
- Fix: Check installationId when receiving a new notification. Only process notifications where the notificationId matches the current installationId.

## Engage Digital Messaging - Android 1.4.1 (November 28th, 2016) ##
- Fix: In the case no welcome message has been defined, the application was displaying a message containg the string "null". This is now fixed.

## Engage Digital Messaging - Android 1.4.0 (November 24th, 2016) ##
- Feature: Add ability to define a welcome message which is automatically displayed when a conversation is empty.
- Improvements: Some performance, security and accessibility improvements.

## Engage Digital Messaging - Android 1.3.1 (November 3rd, 2016) ##
- Fix: Do not strip whitespaces and newlines from JWT dictionary

## Engage Digital Messaging - Android 1.3.0 (October 19th, 2016) ##
- Feature: Add the UnreadCount feature to poll the number of unread messages.

## Engage Digital Messaging - Android 1.2.3 (October 11th, 2016) ##
- Feature: Allow customization of text size.

## Engage Digital Messaging - Android 1.2.2.2 (September 09th, 2016) ##
- Fix: Messages are now always correctly received and sent after internet recovery.
- Fix: Activity mode is now compatible with host applications that are not using AppCompat (Fixed crash when uploading an attachment)

## Engage Digital Messaging - Android 1.2.2.1 (August 25th, 2016) ##
- Fix: Messages are now correctly received and sent after internet recovery (when starting offline).

## Engage Digital Messaging - Android 1.2.2 (July 11th, 2016) ##
- Fix: Upgrade gradle to fix potential issues with native libraries.

## Engage Digital Messaging - Android 1.2.1 (July 5th, 2016) ##
- Fix: "Share" feature (removed hard-coded reference to autorithy `com.dimelo.fileprovider`).
- Fix: Use custom inherited FileProvider class to prevent conflicts.


## Engage Digital Messaging - Android 1.2.0 (May 19th, 2016) ##
- Feature: Remove local cache file
- Feature: Allow customization of attachments icon
- Fix: Compatibility with a wider range of Android Support libraries

## Engage Digital Messaging - Android 1.1.4 (May 19th, 2016) ##
- Fix: button geometry with Android API 19
- FIx: layout size calculation with Android Support Library > 23.3.0

## Engage Digital Messaging - Android 1.1.3 (May 11th, 2016) ##
- Fix: compatibility with Android Support Library > 23.1

## Engage Digital Messaging - Android 1.1.2 (April 14th, 2016) ##
- Feature: It is now possible to customize text message and attachments background with different bubbles
- Feature: It is now possible to customize the color the send message arrow when disabled (no text & no attachment selected)
- Fix: Fixed crash which occured when the SDK was used without `com.google.android.geo.API_KEY`

## Engage Digital Messaging - Android 1.1.1 (January 13th, 2016) ##
- Fix: Fixed crash when calling setUserIdentifier or setJwt after first chat setup.

## Engage Digital Messaging - Android 1.1.0 (December 18th, 2015) ##
- Feature: Added support for image and location attachments.


## Engage Digital Messaging - Android 1.0.0 (July 7th, 2015) ##
- Feature: First official release supporting Dimelo Mobile protocol but limited to text interaction.
