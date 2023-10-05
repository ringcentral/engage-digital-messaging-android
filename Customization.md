Engage Digital Messaging Customization
======================================

Engage Digital Messaging is customizable either from Android resource folder (XML) or programmatically

This file shows a list of attributes you can override in order to customize the threads list and the chat.

# Attributes < string />

### Notification Channel Name
Name of the notification Channel (android_version >= 26).

Xml attribute name: dimelo\_notification\_channel\_name

Programmatically: None

Default: Application name

# Attributes < bool />

### Toolbar Title display
Specify if the title of the toolbar must be displayed (ChatActivity only).

Xml attribute name: dimelo\_toolbar\_display\_title

Programmatically: None

# Attributes < drawable />

### videoCallRequestButtonImage
A drawable used to represent the button to request a video call.

Xml attribute name: None

Programmatically: use `Customization.setVideoCallRequestButtonImage` method

<p align="center">
   <img src="https://i.postimg.cc/nht3PdW0/video-Call-Request-Button-Image.png"/>
</p>

### createNewThreadImage
A drawable for the create new conversation button.

Xml attribute name: None

Programmatically: use `Customization.setCreateNewThreadImage` method

<p align="center">
   <img src="https://i.postimg.cc/7YFCSpy8/create-New-Thread-Background-Color.png"/>
</p>

### backToAllChatsImage
A drawable to replace the arrow displayed next to the "Back to all chats" text displayed in the header.

Xml attribute name: None

Programmatically: use `Customization.setBackToAllChatsImage` method

<p align="center">
   <img src="https://i.postimg.cc/z3YrnrB2/back-To-All-Chats-Image.png"/>
</p>

<p align="center">
   <img src="https://i.postimg.cc/SRTzCsfm/back-To-All-Chats-Image.png"/>
</p>

### lockedThreadImage
A drawable to indicate that the thread is locked in the threads list view.

Xml attribute name: None

Programmatically: use `Customization.setLockedThreadImage` method

<p align="center">
   <img src="https://i.postimg.cc/PxXTmMxk/locked-Thread-Image-Tint-Color.png"/>
</p>

### Toolbar Navigation Icon drawable
Specify a drawable to use for the navigation icon of the toolbar (ChatActivity only).

Xml attribute name: dimelo\_navigation\_icon

Programmatically: None

### Toolbar Background drawable
Specify a drawable to use for the toolbar (ChatActivity only).
The drawable can be tinted with dimelo\_toolbar\_background\_drawable\_tint.

Xml attribute name: dimelo\_toolbar\_background\_drawable

Programmatically: None

### Open gallery drawable icon
Specify a drawable to use for the open gallery icon.

Programmatically: use `Customization.setOpenGalleryIcon` method

<p align="center">
   <img src="https://i.postimg.cc/WtLQ8cbf/Open-Gallery-Icon.png"/>
</p>

### webViewCloseButtonIcon
Drawable used to represent the webView "close" button that is displayed in the header.

Programmatically: use `Customization.setWebViewCloseButtonIcon` method

<p align="center">
   <img src="https://i.postimg.cc/3R68GL0w/web-View-Close-Icon.png"/>
</p>

### webViewPreviousButtonIcon
Drawable used to represent the webView "previous" button that is displayed in the header.

Programmatically: use `Customization.setWebViewPreviousButtonIcon` method

<p align="center">
   <img src="https://i.postimg.cc/htjrTx4Y/previous-Web-View-Icon.png"/>
</p>

### webViewNextButtonIcon
Drawable used to represent the webView "next" button that is displayed in the header.

Programmatically: use `Customization.setWebViewNextButtonIcon` method

<p align="center">
   <img src="https://i.postimg.cc/sxmYZfky/forward-Web-View-Icon.png"/>
</p>

# Attributes < color />

### videoCallRequestButtonTintColor
Color applied to the video call request button.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_video\_call\_request\_button\_tint\_color

Programmatically: set `Customization.videoCallRequestButtonTintColor` property.

<p align="center">
   <img src="https://i.postimg.cc/XJfmhMZT/video-Call-Request-Button-Tint-Color.png"/>
</p>

### deletedMessageBackgroundColor
Color applied to the background of a message that was deleted by its author.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_deleted\_message\_background\_color

Programmatically: set `Customization.deletedMessageBackgroundColor` property.

<p align="center">
   <img src="https://i.postimg.cc/CKj3MgJL/deleted-Message-Background-Color.png"/>
</p>

### deletedMessageTextColor
Color applied to the text of a message that was deleted by its author.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_deleted\_message\_text\_color

Programmatically: set `Customization.deletedMessageTextColor` property.

<p align="center">
   <img src="https://i.postimg.cc/7L3ZFj2S/deleted-Message-Text-Color.png"/>
</p>

### selectedMessageCellBackgroundColor
Color applied to the background of a selected message's cell.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_selected\_message\_cell\_background\_color

Programmatically: set `Customization.selectedMessageCellBackgroundColor` property.

<p align="center">
   <img src="https://i.postimg.cc/sfw4FNPF/selected-Message-Cell-Background-Color.png"/>
</p>


### videoCallRequestedStatusMessageTextColor
Color applied to the status message text when a video call is requested.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_video\_call\_requested\_status\_message\_text\_color

Programmatically: set `Customization.videoCallRequestedStatusMessageTextColor` property.

<p align="center">
   <img src="https://i.postimg.cc/tCpm2qMY/video-Call-Requested-Status-Message-Text-Color.png"/>
</p>

### threadsListCompanyMessageBackgroundColor
Background color of the company message displayed in the threads list.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_threads\_list\_company\_message\_background\_color

Programmatically: set `Customization.threadsListCompanyMessageBackgroundColor` property.

<p align="center">
   <img src="https://i.postimg.cc/13p3xx3b/threads-List-Company-Message-Background-Color.png"/>
</p>

### threadsListCompanyMessageTitleTextColor
Text color applied to the title of the company message that is displayed in the threads list.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_threads\_list\_company\_message\_title\_text\_color

Programmatically: set `Customization.threadsListCompanyMessageTitleTextColor` property.

<p align="center">
   <img src="https://i.postimg.cc/7P261Tyx/threads-List-Company-Message-Title-Text-Color.png"/>
</p>

### threadsListCompanyMessageSubtitleTextColor
Text color applied to the subtitle of the company message that is displayed in the threads list.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_threads\_list\_company\_message\_subtitle\_text\_color

Programmatically: set `Customization.threadsListCompanyMessageSubtitleTextColor` property.

<p align="center">
   <img src="https://i.postimg.cc/k4W0GCkd/threads-List-Company-Message-Subtitle-Text-Color.png"/>
</p>

### webViewProgressBarColor
Color applied to the horizontal and the circular progress bar that is displayed in the webView when the page is loading or when internet is down.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_web\_view\_progress\_bar\_color

Programmatically: set `Customization.webViewProgressBarColor` property.

<p align="center">
   <img src="https://i.postimg.cc/k4r9X20V/web-View-Progress-Bar-Color.png"/>
</p>

<p align="center">
   <img src="https://i.postimg.cc/LXV7Kh2F/web-View-Progress-Bar-Color2.png"/>
</p>

### webViewTitleTextColor
Color applied to the webView title.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_web\_view\_title\_text\_color

Programmatically: set `Customization.webViewTitleTextColor` property.

<p align="center">
   <img src="https://i.postimg.cc/3RLBFG3N/web-View-Title-Text-Color.png"/>
</p>

### webViewNextPreviousButtonIconDisabledColor
Color applied to the disabled webView "previous" and "next" image.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_web\_view\_next\_previous\_button\_icon\_disabled\_color

Programmatically: set `Customization.webViewNextPreviousButtonIconDisabledColor` property.

<p align="center">
   <img src="https://i.postimg.cc/jSr1MBp7/forward-Previous-Icon-Disabled-Color.png"/>
</p>

### webViewNextPreviousButtonIconEnabledColor
Color applied to the enabled webView "previous" and "next" image.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_web\_view\_next\_previous\_button\_icon\_enabled\_color

Programmatically: set `Customization.webViewNextPreviousButtonIconEnabledColor` property.

<p align="center">
   <img src="https://i.postimg.cc/QtP41zgV/forward-Previous-Icon-Enabled-Color.png"/>
</p>

### webViewHeaderBackgroundColor
Color applied to the webView header background.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_web\_view\_Header\_background\_color

Programmatically: set `Customization.webViewHeaderBackgroundColor` property.

<p align="center">
   <img src="https://i.postimg.cc/pXBQt798/web-View-Header-Background-Color.png"/>
</p>

### webViewBodyBackgroundColor
Color applied to the webView body background.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_web\_view\_body\_background\_color

Programmatically: set `Customization.webViewBodyBackgroundColor` property.

<p align="center">
   <img src="https://i.postimg.cc/L5DJGcy8/web-View-Body-Background-Color.png"/>
</p>

### badgeTextColor
Text color for the badge text view.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_badge\_text\_color

Programmatically: set `Customization.badgeTextColor` property.

<p align="center">
   <img src="https://i.postimg.cc/nVW07cRd/badge.png"/>
</p>

<p align="center">
   <img src="https://i.postimg.cc/Xvn83Zqv/badge.png"/>
</p>

<p align="center">
   <img src="https://i.postimg.cc/500SYZwd/badge.png"/>
</p>

### badgeBackgroundColor
Background color for the badge text view.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_badge\_background\_color

Programmatically: set `Customization.badgeBackgroundColor` property.

<p align="center">
   <img src="https://i.postimg.cc/nVW07cRd/badge.png"/>
</p>

<p align="center">
   <img src="https://i.postimg.cc/Xvn83Zqv/badge.png"/>
</p>

<p align="center">
   <img src="https://i.postimg.cc/500SYZwd/badge.png"/>
</p>

### createNewThreadImageColor
Color for the create new thread image.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_create\_new\_thread\_image\_color

Programmatically: set `Customization.createNewThreadImageColor` property.

<p align="center">
   <img src="https://i.postimg.cc/432bRs07/create-New-Thread-Image-Color.png"/>
</p>

### threadsListSeparatorColor
Color for the threads list separator.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_threads\_list\_separator\_color

Programmatically: set `Customization.threadsListSeparatorColor` property.

<p align="center">
   <img src="https://i.postimg.cc/9FJTTxQc/threads-List-Separator-Color.png"/>
</p>

### lockedThreadImageTintColor
Tint color for the locked thread image in the threads list view.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_locked\_thread\_image\_tint\_color

Programmatically: set `Customization.lockedThreadImageTintColor` property.

<p align="center">
   <img src="https://i.postimg.cc/PxXTmMxk/locked-Thread-Image-Tint-Color.png"/>
</p>

### threadsListRefreshControlTintColors
Tint colors array for the threads list refresh control.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: None

Programmatically: set `Customization.threadsListRefreshControlTintColors` property.

<p align="center">
   <img src="https://i.postimg.cc/76w00j0Y/threads-List-Refresh-Control-Tint-Color.png"/>
</p>

### createNewThreadBackgroundColor
Background color for the create new conversation button.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_create\_new\_thread\_background\_color

Programmatically: set `Customization.createNewThreadBackgroundColor` property.

<p align="center">
   <img src="https://i.postimg.cc/7YFCSpy8/create-New-Thread-Background-Color.png"/>
</p>

### threadsListBackgroundColorSelection
Background color for the threads list selected item.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_threads\_list\_background\_color\_selection

Programmatically: set `Customization.threadsListBackgroundColorSelection` property.

<p align="center">
   <img src="https://i.postimg.cc/5tNFt8V6/threads-List-Background-Color-Selection.png"/>
</p>

### threadsListAgentNameTextColor
Text color for the agent name displayed in the threads list.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_threads\_list\_agent\_name\_text\_color

Programmatically: set `Customization.threadsListAgentNameTextColor` property.

<p align="center">
   <img src="https://i.postimg.cc/qBLVsnVk/threads-List-Agent-Name-Text-Color.png"/>
</p>

### threadsListMessageTextColor
Text color for the message displayed in the threads list.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_threads\_list\_message\_text\_color

Programmatically: set `Customization.threadsListMessageTextColor` property.

<p align="center">
   <img src="https://i.postimg.cc/bYLWDhkr/threads-List-Message-Text-Color.png"/>
</p>

### threadsListDateTextColor
Text color for the date displayed in the threads list.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_threads\_list\_date\_text\_color

Programmatically: set `Customization.threadsListDateTextColor` property.

<p align="center">
   <img src="https://i.postimg.cc/L50xym3V/threads-List-Date-Text-Color.png"/>
</p>

### fragmentHeaderColor
Color for the fragment header.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_fragment\_header\_color

Programmatically: set `Customization.fragmentHeaderColor` property.

<p align="center">
   <img src="https://i.postimg.cc/VvL7pZhs/fragment-Header-Color.png"/>
</p>

### Toolbar Background drawable tint
Specify a tint for the drawable used as a background for the toolbar (ChatActivity only).

Xml attribute name: dimelo\_toolbar\_background\_drawable\_tint

Programmatically: None

### Toolbar Background color
Background color of toolbar (ChatActivity only).

Xml attribute name: dimelo\_toolbar\_background\_color

Programmatically: None

### InputBar background color
Background color for the input bar.

Color must be in hex format, e.g. `#007AFF`.
Xml attribute name: dimelo\_inputbar\_background\_color

Programmatically: set `Customization.inputbarBackgroundColor` property

### webViewCloseButtonIconColor
Color applied to the webView "close" image.

If not specified, white color is applied

Color must be in hex format, e.g. `#007AFF`

Xml attribute name: rc\_web\_view\_close\_button\_icon\_color

Programmatically: set `Customization.webViewCloseButtonIconColor` property.

<p align="center">
   <img src="https://i.postimg.cc/635JYFG0/web-View-Close-Icon-Color.png"/>
</p>

### Open gallery icon color
Define the icon color of the open gallery button.

If not specified, white color is applied

Color must be in hex format, e.g. `#007AFF`

Xml attribute name: rc\_open\_gallery\_icon\_color

Programmatically: set `Customization.openGalleryIconColor` property.

<p align="center">
   <img src="https://i.postimg.cc/gk2RcLzj/open-Gallery-Icon-Color.png"/>
</p>

### Open gallery background color
Define the background color of the open gallery button.

If not specified, `#4481EB` color is applied

Color must be in hex format, e.g. `#007AFF`

Xml attribute name: rc\_open\_gallery\_background\_color

Programmatically: set `Customization.openGalleryBackgroundColor` property.

<p align="center">
   <img src="https://i.postimg.cc/5NdGZ1bs/open-Gallery-Background-Color.png"/>
</p>

### Send Button enabled color
Define the color of the send button when a message can be sent.

If not specified, main theme color is applied

Color must be in hex format, e.g. `#007AFF`

Xml attribute name: dimelo\_send\_button\_enabled\_color

Programmatically: use `Customization.setSendButtonEnabledColor` method

### Send Button disabled color
Define the color the send button when no text is written and no attachment is selected.

Color must be in hex format, e.g. `#007AFF`

Xml attribute name: dimelo\_send\_button\_disabled\_color

Programmatically: use `Customization.setSendButtonDisabledColor` method

### Bottom sheet enabled state icons color
Define the color of the icons placed in the bottom sheet when they are enabled.

If not specified, main theme color is applied.

Color must be in hex format, e.g. `#007AFF`

Xml attribute name: dimelo\_bottom\_sheet\_icons\_enabled\_color

Programmatically: use `Customization.setBottomSheetIconsEnabledColor` method

### attachment Icon Button
Specify a drawable to use for the attachment icon.

Programmatically: use `Customization.setAttachmentIcon` method

### document Icon Button
Specify a drawable to use for the document icon.

Programmatically: use `Customization.setAttachmentDocumentIcon` method

### Bottom sheet disabled state icons color
Define the color of the icons placed in the bottom sheet when they are disabled.

Color must be in hex format, e.g. `#007AFF`

Xml attribute name: dimelo\_bottom\_sheet\_icons\_disabled\_color

Programmatically: use `Customization.setBottomSheetIconsDisabledColor` method

### Bottom sheet disabled state icons color
Define the color of the icons placed in the bottom sheet when they are disabled.

Color must be in hex format, e.g. `#007AFF`

Xml attribute name: dimelo\_bottom\_sheet\_icons\_disabled\_color

Programmatically: use `Customization.setBottomSheetIconsDisabledColor` method

### ActionBar background color
ActionBar color (ChatActivity only).

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_toolbar\_background\_color

Programmatically: None

### chat background color
Background color of the chat.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_background\_color

Programmatically: set `Customization.backgroundColor` property

### user message TextColor
Foreground color for user's message text.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_user\_message\_text\_color

Programmatically: set `Customization.userMessageTextColor` property

### agent message TextColor
Foreground color for agent's message text.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_agent\_message\_text\_color

Programmatically: set `Customization.agentMessageTextColor` property

### system message TextColor
Foreground color for system's message text.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_system\_message\_text\_color

Programmatically: set `Customization.systemMessageTextColor` property

### error icon color
Define the color of the error icon when the message is not sent.

Color must be in hex format, e.g. `#007AFF`

Xml attribute name:  dimelo\_error\_icon\_color

Programmatically: use `Customization.errorIconColor` method

### navigation bar title color
Text color for navigation bar title.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_navigation\_bar\_title\_color

Programmatically: set `Customization.navigationBarTitleColor` property

### navigation bar item tint color (share icon)
Tint color for navigation bar item.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_navigation\_bar\_item\_tint\_color

Programmatically: set `Customization.navigationBarItemTintColor` property

### Notes

- For the back item tint color customization, you can use this code into your application (it will be applied for all activities)

   ```java
   Drawable backItem = getResources().getDrawable(R.drawable.abc_ic_ab_back_mtrl_am_alpha);
   backItem.setColorFilter(your_color, PorterDuff.Mode.SRC_IN);
   getSupportActionBar().setHomeAsUpIndicator(backItem);
   ```

- You can directly apply a custom theme if it's supported without using `Customization.navigationBarItemTintColor` and `Customization.navigationBarTitleColor`

 1. Add this code to your custom theme in **themes.xml**

      <item name="android:drawableTint">your_navigation_bar_item_tint_color</item>
      <item name="toolbarStyle">@style/toolbar.titleTextStyle</item>
      <item name="android:textColor">your_navigation_bar_Title_color</item>
      <style name="toolbar.titleTextStyle" parent="@style/Widget.AppCompat.Toolbar" />

  2.  Apply your custom theme to the activity in **AndroidManifest.xml**

      * For ChatActivity

         ```xml
         <activity android:name="com.dimelo.dimelosdk.main.ChatActivity"
                      tools:replace="android:theme"
                      android:theme="@style/your_theme">
         </activity>
         ```

      * For AttachmentActivity

         ```xml
         <activity android:name="com.dimelo.dimelosdk.main.AttachmentActivity"
                      tools:replace="android:theme"
                      android:theme="@style/your_theme">
         </activity>
         ```

       - You should use `tools:replace="android:theme"` to replace the default Dimelo theme

### user message BackgroundColor
Background color for user message bubbles.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_user\_bubble\_color

Programmatically: set this property by calling `Customization.setUserMessageBubbleDrawable` method.

### welcomeMessageTextColor
Text color for welcome message.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_welcome\_message\_text\_color

Programmatically: set `Customization.welcomeMessageTextColor` property.

<p align="center">
   <img src="https://i.postimg.cc/rsGf5nNp/welcome-Message-Text-Color.png"/>
</p>

### agentTimeColor
Text color for the agent time text view.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_agent\_time\_color

Programmatically: set `Customization.agentTimeColor` property.

<p align="center">
   <img src="https://i.postimg.cc/MT77LcMP/agent-Time-Color.png"/>
</p>

### hourTimeTextColor
Text color for the hour text view.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_hour\_time\_text\_color

Programmatically: set `Customization.hourTimeTextColor` property.

<p align="center">
   <img src="https://i.postimg.cc/05Jh7w1j/hour-Time-Text-Color.png"/>
</p>

### agentTemplateBorderColor
Border color for agent structured message bubbles.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_agent\_template\_border\_color

Programmatically: set `Customization.agentTemplateBorderColor` property.

<p align="center">
   <img src="https://i.postimg.cc/g0DcBmcy/agent-Template-Border-Color.png"/>
</p>

### agentTemplateWithImageBodyBackgroundColor
Background color for agent structured message. Only applies when there is an image, otherwise, please see `agentStructuredMessageBodyBackgroundColor`.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_agent\_template\_with\_image\_body\_background\_color

Programmatically: set `Customization.agentTemplateWithImageBodyBackgroundColor` property.

<p align="center">
   <img src="https://i.postimg.cc/D0bTFThM/agent-Template-With-Image-Body-Background-Color.png"/>
</p>

### agentStructuredMessageBodyBackgroundColor
Background color for body agent structured message view. Only applies when there is no image, otherwise, please see `agentTemplateWithImageBodyBackgroundColor`.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_agent\_structured\_message\_body\_background\_color

Programmatically: set `Customization.agentStructuredMessageBodyBackgroundColor` property.

<p align="center">
   <img src="https://i.postimg.cc/R0FC82Wj/agent-Structured-Message-Body-Background-Color.png"/>
</p>

### agent message BackgroundColor
Background color for agent message bubbles.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_agent\_bubble\_color

Programmatically: set this property by calling `Customization.setAgentMessageBubbleDrawable` method.

### system message BackgroundColor
Background color for system message bubbles.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_system\_bubble\_color

Programmatically: set this property by calling `Customization.setSystemMessageBubbleDrawable` method.

### user attachment bubbles BackgroundColor
Background color for user attachment bubbles.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_user\_attachment\_bubble\_color

Programmatically: set this property by calling `Customization.setUserAttachmentBubbleDrawable` method.

### agent attachment bubbles BackgroundColor
Background color for agent attachment bubbles.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_agent\_attachment\_bubble\_color

Programmatically: set this property by calling `Customization.setAgentAttachmentBubbleDrawable` method.

### agentStructuredMessageUrlMarginTop
Margin top for structured message url text view.

Xml attribute name: dimen/rc_agent_structured_message_url_margin_top

Programmatically: set `Customization.agentStructuredMessageUrlMarginTop` property.

<p align="center">
   <img src="https://i.postimg.cc/c1nDwmxW/agent-Structured-Message-Url-Margin-Top.png"/>
</p>

### agentStructuredMessageSubtitleMarginTop
Margin top for structured message subtitle text view.

Xml attribute name: dimen/rc_agent_structured_message_subtitle_margin_top

Programmatically: set `Customization.agentStructuredMessageSubtitleMarginTop` property.

<p align="center">
   <img src="https://i.postimg.cc/NFkmbLC6/agent-Structured-Message-Subtitle-Margin-Top.png"/>
</p>

### agentStructuredMessageTitleColor
Foreground color for agent's structured message title text.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_agent\_structured\_message\_title\_color

Programmatically: set `Customization.agentStructuredMessageTitleColor` property.

<p align="center">
   <img src="https://i.postimg.cc/xdQYVC6J/Capture-d-e-cran-2020-11-22-a-15-25-17.png"/>
</p>

### agentStructuredMessageSubtitleColor
Foreground color for agent's structured message subtitle text.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_agent\_structured\_message\_subtitle\_color

Programmatically: set `Customization.agentStructuredMessageSubtitleColor` property.

<p align="center">
   <img src="https://i.postimg.cc/Kc1YN1wx/agent-Structured-Message-Subtitle-Color.png"/>
</p>

### agentStructuredMessageUrlColor
Foreground color for agent's structured message url text.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_agent\_structured\_message\_url\_color

Programmatically: set `Customization.agentStructuredMessageUrlColor` property.

<p align="center">
   <img src="https://i.postimg.cc/NFXBwHvX/agent-Structured-Message-Url-Color.png"/>
</p>

### agentStructuredMessageItemColor
Foreground color for agent's structured message item text.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_agent\_structured\_message\_item\_color

Programmatically: set `Customization.agentStructuredMessageItemColor` property.

<p align="center">
   <img src="https://i.postimg.cc/3x85t6Nm/agent-Structured-Message-Item-Color.png"/>
</p>

### agentStructuredMessageItemTappedColor
Foreground color for agent's structured message tapped item text.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Programmatically: set `Customization.agentStructuredMessageItemTappedColor` property.

<p align="center">
   <img src="https://i.postimg.cc/3x85t6Nm/agent-Structured-Message-Item-Color.png"/>
</p>

### agentStructuredMessageItemBackgroundColor
Background color for agent's structured message item text.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_agent\_structured\_message\_item\_background\_color

Programmatically: set `Customization.agentStructuredMessageItemBackgroundColor` property.

<p align="center">
   <img src="https://i.postimg.cc/xCH4fyq9/agent-Structured-Message-Item-Background-Color.png"/>
</p>

### agentStructuredMessageItemTappedBackgroundColor
Background color for agent's structured message tapped item.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_agent\_structured\_message\_item\_tapped\_background\_color

Programmatically: set `Customization.agentStructuredMessageItemTappedBackgroundColor` property.

<p align="center">
   <img src="https://i.postimg.cc/xCH4fyq9/agent-Structured-Message-Item-Background-Color.png"/>
</p>

### quickRepliesBorderWidth
Border width for quick replies.

Xml attribute name: dimen/rc_quick_replies_border_width

Programmatically: set `Customization.quickRepliesBorderWidth` property.

<p align="center">
   <img src="https://i.postimg.cc/4y2z810M/quick-replies-border-width.png"/>
</p>

### quickRepliesHorizontalSpacing
Horizontal spacing for quick replies.

Xml attribute name: dimen/rc_quick_replies_horizontal_spacing

Programmatically: set `Customization.quickRepliesHorizontalSpacing` property.

<p align="center">
   <img src="https://i.postimg.cc/7YZsmGpS/quick-replies-horizontal-spacing.png"/>
</p>

### quickRepliesVerticalSpacing
Vertical spacing for quick replies.

Xml attribute name: dimen/rc_quick_replies_vertical_spacing

Programmatically: set `Customization.quickRepliesVerticalSpacing` property.

<p align="center">
   <img src="https://i.postimg.cc/3rjpd3J6/quick-replies-vertical-spacing.png"/>
</p>

### quickRepliesBorderColor
Border color for quick replies.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_quick\_replies\_border\_color

Programmatically: set `Customization.quickRepliesBorderColor` property.

<p align="center">
   <img src="https://i.postimg.cc/v84LBJ6w/quick-replies-border-color.png"/>
</p>

### quickRepliesTappedBorderColor
 Border color for tapped quick replies.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_quick\_replies\_tapped\_border\_color

Programmatically: set `Customization.quickRepliesTappedBorderColor` property.

### quickRepliesTextColor
Text color for quick replies.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_quick\_replies\_text\_color

Programmatically: set `Customization.quickRepliesTextColor` property.

<p align="center">
   <img src="https://i.postimg.cc/8zN6h9s5/quick-replies-text-color.png"/>
</p>

### quickRepliesTappedTextColor
Text color for tapped quick replies.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_quick\_replies\_tapped\_text\_color

Programmatically: set `Customization.quickRepliesTappedTextColor` property.

### quickRepliesBackgroundColor
Background color for quick replies.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_quick\_replies\_background\_color

Programmatically: set `Customization.quickRepliesBackgroundColor` property.

<p align="center">
   <img src="https://i.postimg.cc/hvRjKQdj/quick-replies-background-color.png"/>
</p>

### quickRepliesTappedBackgroundColor
Background color for tapped quick replies.

Color must be in hex format, e.g. `007AFF` or `#007AFF`.

Xml attribute name: rc\_quick\_replies\_tapped\_background\_color

Programmatically: set `Customization.quickRepliesTappedBackgroundColor` property.

### date TextColor
Text color for the date label.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_date\_color

Programmatically: set `Customization.dateTextColor` property.

### agentStructuredMessageTitleFont
Font for agent's structured message title.

Programmatically: set `Customization.agentStructuredMessageTitleFont` property

Xml attribute name: None

<p align="center">
   <img src="https://i.postimg.cc/htZmjk70/agent-Structured-Message-Title-Font.png"/>
</p>

### agentStructuredMessageSubTitleFont
Font for agent's structured message subtitle.

Programmatically: set `Customization.agentStructuredMessageSubTitleFont` property

Xml attribute name: None

<p align="center">
   <img src="https://i.postimg.cc/JnLz4xKq/agent-Structured-Message-Sub-Title-Font.png"/>
</p>

### agentStructuredMessageUrlFont
Font for agent's structured message url.

Programmatically: set `Customization.agentStructuredMessageUrlFont` property

Xml attribute name: None

<p align="center">
   <img src="https://i.postimg.cc/j5ctqbDx/agent-Structured-Message-Url-Font.png"/>
</p>

### agentStructuredMessageItemFont
Font for agent's structured message item.

Programmatically: set `Customization.agentStructuredMessageItemFont` property

Xml attribute name: None

<p align="center">
   <img src="https://i.postimg.cc/6QLNzXLr/agent-Structured-Message-Item-Font.png"/>
</p>

### agentTimeFont
Font for the agent time text view.

Programmatically: set `Customization.agentTimeFont` property

Xml attribute name: None

<p align="center">
   <img src="https://i.postimg.cc/ncQg0xnX/agent-Time-Font.png"/>
</p>

### hourTimeFont
Font for the hour text view.

Programmatically: set `Customization.hourTimeFont` property

Xml attribute name: None

<p align="center">
   <img src="https://i.postimg.cc/MXkshczv/hour-Time-Font.png"/>
</p>

### webViewTitleFont
Font applied to the webView title.

Programmatically: set `Customization.webViewTitleFont` property

Xml attribute name: None

<p align="center">
   <img src="https://i.postimg.cc/v8tXQDkc/web-View-Title-Font.png"/>
</p>


### videoCallRequestedStatusMessageTextFont
Font applied to the status message when a video call is requested.

Programmatically: set `Customization.videoCallRequestedStatusMessageTextFont` property

Xml attribute name: None

<p align="center">
   <img src="https://i.postimg.cc/zfDVDgvT/video-Call-Requested-Status-Message-Text-Font.png"/>
</p>

### deletedMessageTextFont
Font applied to to a message that was deleted by its author.

Programmatically: set `Customization.deletedMessageTextFont` property

Xml attribute name: None

<p align="center">
   <img src="https://i.postimg.cc/Nj714CjP/deleted-Message-Text-Font.png"/>
</p>

### agent Name color
Text color for agent's name.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_agent\_name\_color

Programmatically: set `Customization.agentNameColor`  property

# Attributes < dimen />

### User Bubble padding

Padding of the user's message bubble.

Xml attributes name:

- dimelo\_user\_message\_bubble\_left\_padding

- dimelo\_user\_message\_bubble\_right\_padding

- dimelo\_user\_message\_bubble\_top\_padding

- dimelo\_user\_message\_bubble\_bottom\_padding

Programmatically: set `Customization.userMessageBubblePadding` property

### Agent Bubble padding

Padding of the agent's message bubble.

Xml attributes name:

- dimelo\_agent\_message\_bubble\_left\_padding

- dimelo\_agent\_message\_bubble\_right\_padding

- dimelo\_agent\_message\_bubble\_top\_padding

- dimelo\_agent\_message\_bubble\_bottom\_padding

Programmatically: set `Customization.agentMessageBubblePadding` property

### System Bubble padding

Padding of the system's message bubble.

Xml attributes name:

- dimelo\_system\_message\_bubble\_left\_padding

- dimelo\_system\_message\_bubble\_right\_padding

- dimelo\_system\_message\_bubble\_top\_padding

- dimelo\_system\_message\_bubble\_bottom\_padding

Programmatically: set `Customization.systemMessageBubblePadding` property

### User Attachment Bubble padding

Padding of the user's attachment bubble.

Xml attributes name:

- dimelo\_user\_attachment\_bubble\_left\_padding

- dimelo\_user\_attachment\_bubble\_right\_padding

- dimelo\_user\_attachment\_bubble\_top\_padding

- dimelo\_user\_attachment\_bubble\_bottom\_padding

Programmatically: set `Customization.userAttachmentBubblePadding` property

### Agent Attachment Bubble padding

Padding of the agent's attachment bubble.

Xml attributes name:

- dimelo\_agent\_attachment\_bubble\_left\_padding

- dimelo\_agent\_attachment\_bubble\_right\_padding

- dimelo\_agent\_attachment\_bubble\_top\_padding

- dimelo\_agent\_attachment\_bubble\_bottom\_padding

Programmatically: set `Customization.agentAttachmentBubblePadding` property

### System Attachment Bubble padding

Padding of the system's attachment bubble.

Xml attributes name:

- dimelo\_system\_attachment\_bubble\_left\_padding

- dimelo\_system\_attachment\_bubble\_right\_padding

- dimelo\_system\_attachment\_bubble\_top\_padding

- dimelo\_system\_attachment\_bubble\_bottom\_padding

Programmatically: set `Customization.systemAttachmentBubblePadding` property

### agentStructuredMessageBodyPadding
Padding of the agent structured message bubbles.

Xml attributes name:

- rc\_agent\_structured\_message\_body\_left\_padding

- rc\_agent\_structured\_message\_body\_right\_padding

- rc\_agent\_structured\_message\_body\_top\_padding

- rc\_agent\_structured\_message\_body\_bottom\_padding

Programmatically: set `Customization.agentStructuredMessageBodyPadding` property

<p align="center">
   <img src="https://i.postimg.cc/JzXyrsMR/agent-Structured-Message-Body-Padding.png"/>
</p>

### agentStructuredMessageItemPadding
Padding of the agent structured message item.

Xml attributes name:

- rc\_agent\_structured\_message\_item\_left\_padding

- rc\_agent\_structured\_message\_item\_right\_padding

- rc\_agent\_structured\_message\_item\_top\_padding

- rc\_agent\_structured\_message\_item\_bottom\_padding

Programmatically: set `Customization.agentStructuredMessageItemPadding` property

<p align="center">
   <img src="https://i.postimg.cc/L6Y5DJqj/agent-Structured-Message-Item-Padding.png"/>
</p>

### quickRepliesItemPadding
Padding of the quick replies item.

Xml attributes name:

- rc\_quick\_replies\_item\_left\_padding

- rc\_quick\_replies\_item\_right\_padding

- rc\_quick\_replies\_item\_top\_padding

- rc\_quick\_replies\_item\_bottom\_padding

Programmatically: set `Customization.quickRepliesItemPadding` property

<p align="center">
   <img src="https://i.postimg.cc/bYBWLmVH/quick-replies-item-padding.png"/>
</p>

### agentTimePadding
Padding for agent time text view.

Xml attributes name:

- rc\_agent\_time\_left\_padding

- rc\_agent\_time\_right\_padding

- rc\_agent\_time\_top\_padding

- rc\_agent\_time\_bottom\_padding

Programmatically: set `Customization.agentTimePadding` property

<p align="center">
   <img src="https://i.postimg.cc/BvVQ2sqm/agent-Time-Padding.png"/>
</p>

# Date Format

### dateFormatter
Date format for the date label (should be a `SimpleDateFormat`).

Programmatically: set `Customization.dateFormatter` property

Xml attribute name: None

*Note:* This is an example on how to initialize `Customization.dateFormatter`:
```java
SimpleDateFormat dateFormatter = new SimpleDateFormat("dd-MM-yyyy");
RcFragment.Customization customisation = RcFragment.getCustomization();
customisation.dateFormatter = dateFormatter;
```

# Typeface

### threadsListCompanyMessageTitleFont
Font used for the company message title that is displayed in the threads list.

Programmatically: set `Customization.threadsListCompanyMessageTitleFont` property

Xml attribute name: None

<p align="center">
   <img src="https://i.postimg.cc/wTnQfN10/threads-List-Company-Message-Title-Font.png"/>
</p>

### threadsListCompanyMessageSubtitleFont
Font used for the company message subtitle that is displayed in the threads list.

Programmatically: set `Customization.threadsListCompanyMessageSubtitleFont` property

Xml attribute name: None

<p align="center">
   <img src="https://i.postimg.cc/4dnKR8Mt/threads-List-Company-Message-Subtitle-Font.png"/>
</p>

### badgeFont
Badge text font.

Programmatically: set `Customization.badgeFont` property

Xml attribute name: None

<p align="center">
   <img src="https://i.postimg.cc/nVW07cRd/badge.png"/>
</p>

<p align="center">
   <img src="https://i.postimg.cc/Xvn83Zqv/badge.png"/>
</p>

<p align="center">
   <img src="https://i.postimg.cc/500SYZwd/badge.png"/>
</p>

### backToAllChatsFont
Font for the backToAllChats text view (in the header fragment).

Programmatically: set `Customization.backToAllChatsFont` property

Xml attribute name: None

<p align="center">
   <img src="https://i.postimg.cc/VvL7pZhs/fragment-Header-Color.png"/>
</p>

### threadsListAgentNameFont
Font for the agent name displayed in the threads list.

Programmatically: set `Customization.threadsListAgentNameFont` property

Xml attribute name: None

<p align="center">
   <img src="https://i.postimg.cc/qBLVsnVk/threads-List-Agent-Name-Text-Color.png"/>
</p>

### threadsListMessageFont
Font for the message displayed in the threads list.

Programmatically: set `Customization.threadsListMessageFont` property

Xml attribute name: None

<p align="center">
   <img src="https://i.postimg.cc/bYLWDhkr/threads-List-Message-Text-Color.png"/>
</p>

### threadsListDateFont
Font for the date displayed in the threads list.

Programmatically: set `Customization.threadsListDateFont` property

Xml attribute name: None

<p align="center">
   <img src="https://i.postimg.cc/L50xym3V/threads-List-Date-Text-Color.png"/>
</p>

### navigationBarTitleFont
Font for the navigation bar title (minimum android SDK version equal to 18 when using Dimelo as Fragment, otherwise we use the default font).

Programmatically: set `Customization.navigationBarTitleFont` property

Xml attribute name: None

### messageFont
Font for user and agent messages.

Programmatically: set `Customization.messageFont` property

Xml attribute name: None

### systemMessageFont
Font for system messages.

Programmatically: set `Customization.systemMessageFont` property

Xml attribute name: None

### dateFont
Font for the date label.

Programmatically: set `Customization.dateFont` property

Xml attribute name: None

### agentNameFont
Font for agent's name.

Programmatically: set `Customization.agentNameFont` property

Xml attribute name: None

# Text Size


### videoCallRequestedStatusMessageTextSize
Text size used for the status message when a video call is requested.

Programmatically: set `Customization.videoCallRequestedStatusMessageTextSize` property

Xml attribute name: dimen/rc_video_call_requested_status_message_text_size

<p align="center">
   <img src="https://i.postimg.cc/qBCJcLC1/video-Call-Requested-Status-Message-Text-Size.png"/>
</p>

### deletedMessageTextSize
Text size applied to a message that was deleted by its author.

Programmatically: set `Customization.deletedMessageTextSize` property

Xml attribute name: dimen/rc_deleted_message_text_size

<p align="center">
   <img src="https://i.postimg.cc/4yNq2mDH/deleted-Message-Text-Size.png"/>
</p>

### threadsListCompanyMessageTitleTextSize
Text size used for the company message title that is displayed in the threads list.

Programmatically: set `Customization.threadsListCompanyMessageTitleTextSize` property

Xml attribute name: dimen/rc_threads_list_company_message_title_text_size

<p align="center">
   <img src="https://i.postimg.cc/y6gnzKwf/threads-List-Company-Message-Title-Text-Size.png"/>
</p>

### threadsListCompanyMessageSubtitleTextSize
Text size used for the company message subtitle that is displayed in the threads list.

Programmatically: set `Customization.threadsListCompanyMessageSubtitleTextSize` property

Xml attribute name: dimen/rc_threads_list_company_message_subtitle_text_size

<p align="center">
   <img src="https://i.postimg.cc/fL0d1zJm/threads-List-Company-Message-Subtitle-Text-Size.png"/>
</p>

### webViewTitleTextSize
webView title text size.

Programmatically: set `Customization.webViewTitleTextSize` property

Xml attribute name: dimen/rc_web_view_title_text_size

<p align="center">
   <img src="https://i.postimg.cc/dQhdf3Fb/web-View-Title-Text-Size.png"/>
</p>

### badgeTextSize
Badge text size.

Programmatically: set `Customization.badgeTextSize` property

Xml attribute name: dimen/rc_badge_text_size

### backToAllChatsTextSize
Back to all chats text size.

Programmatically: set `Customization.backToAllChatsTextSize` property

Xml attribute name: dimen/rc_back_to_all_chats_text_size

### threadsListAgentNameTextSize
Text size for the agent name displayed in the threads list.

Programmatically: set `Customization.threadsListAgentNameTextSize` property

Xml attribute name: dimen/rc_threads_list_agent_name_text_size

### threadsListMessageTextSize
Text size of the message displayed in the threads list.

Programmatically: set `Customization.threadsListMessageTextSize` property

Xml attribute name: dimen/rc_threads_list_message_text_size

### threadsListDateTextSize
Text size of the date displayed in the threads list.

Programmatically: set `Customization.threadsListDateTextSize` property

Xml attribute name: dimen/rc_threads_list_date_text_size

### messageTextSize
TextSize for user and agent messages.

Programmatically: set `Customization.messageTextSize` property

Xml attribute name: dimen/dimelo_message_text_size

### systemMessageTextSize
TextSize for system messages.

Programmatically: set `Customization.systemMessageTextSize` property

Xml attribute name: dimen/dimelo_system_message_text_size

### DateTextSize
TextSize for date label.

Programmatically: set `Customization.dateTextSize` property

Xml attribute name: dimen/dimelo_date_text_size

### agentNameTextSize
TextSize for agent name label.

Programmatically: set `Customization.agentNameTextSize` property

Xml attribute name: dimen/dimelo_agent_name_text_size

### messageFieldTextSize
TextSize for the message input.

Programmatically: set `Customization.messageFieldTextSize` property

Xml attribute name: dimen/dimelo_message_field_text_size

### agentTimeTextSize
TextSize for agent time text view.

Programmatically: set `Customization.agentTimeTextSize` property

Xml attribute name: dimen/rc_agent_time_text_size

<p align="center">
   <img src="https://i.postimg.cc/d1kppcGN/agent-Time-Text-Size.png"/>
</p>

### hourTimeTextSize
TextSize for the hour text view.

Programmatically: set `Customization.hourTimeTextSize` property

Xml attribute name: dimen/rc_hour_time_text_size

<p align="center">
   <img src="https://i.postimg.cc/bY1FtTgn/hour-Time-Text-Size.png"/>
</p>

### defaultSize
Set a global size to all the elements for which a text size can be set.

Programmatically: None.

Xml attribute name: dimen/dimelo_default_text_size

# Boolean

### showAgentAvatarImage
Show or hide the agent avatar image.

Must be a boolean, default is `true`.

Programmatically: set `Customization.showAgentAvatarImage` property.

Xml attribute name: None

`showAgentAvatarImage=true`:

<p align="center">
<img src="https://i.postimg.cc/7ZGctkDC/1.png"/>
</p>

`showAgentAvatarImage=false`:

<p align="center">
<img src="https://i.postimg.cc/pdvZQbdM/2.png"/>
</p>
