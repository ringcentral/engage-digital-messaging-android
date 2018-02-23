Dimelo Chat Customization
==========================

Dimelo chat is customizable either from Android resource folder (XML) or programmatically

This file shows a list of attributes you can override in order to customize the chat.

# Attributes < string />

### Toolbar Title String
Title of the conversation window (ChatActiviy only)

Xml attribute name: dimelo\_toolbar\_title

Programmatically: None

### Notification Channel Name
Name of the notification Channel (android_version >= 26)

Xml attribute name: dimelo\_notification\_channel\_name

Programmatically: None

Default: Application name

# Attributes < bool />

### Toolbar Title display
Specify if the title of the toolbar must be displayed (ChatActiviy only)

Xml attribute name: dimelo\_toolbar\_display\_title

Programmatically: None

# Attributes < drawable />

### Toolbar Navigation Icon drawable
Specify a drawable to use for the navigation icon of the toolbar(ChatActivity only)

Xml attribute name: dimelo\_navigation\_icon

Programmatically: None

### Toolbar Background drawable
Specify a drawable to use for the toolbar. (ChatActiviy only)  
The drawable can be tinted with dimelo\_toolbar\_background\_drawable\_tint.

Xml attribute name: dimelo\_toolbar\_background\_drawable

Programmatically: None

# Attributes < color />

### Toolbar Background drawable tint
Specify a tint for the drawable used as a background for the toolbar.(ChatActiviy only)

Xml attribute name: dimelo\_toolbar\_background\_drawable\_tint

Programmatically: None

### Toolbar Background color
Background color of toolbar (ChatActiviy only)

Xml attribute name: dimelo\_toolbar\_background\_color

Programmatically: None

### InputBar background color
Background color for the input bar

Color must be in hex format, e.g. `#007AFF`.
Xml attribute name: dimelo\_inputbar\_background\_color

Programmatically: set `Customization.inputbarBackgroundColor` property

### Send Button enabled color
Define the color the send button when a message can be sent

If not specified, main theme color is applied

Color must be in hex format, e.g. `#007AFF`

Xml attribute name: dimelo\_send\_button\_enabled\_color

Programmmatically: use `Customization.setSendButtonEnabledColor` method

### Send Button disabled color
Define the color the send button when no text is written and no attachment is selected.

Color must be in hex format, e.g. `#007AFF`

Xml attribute name: dimelo\_send\_button\_disabled\_color

Programmmatically: use `Customization.setSendButtonDisabledColor` method

### Bottom sheet enabled state icons color
Define the color the icons icons placed in the bottom sheet when they are enabled

If not specified, main theme color is applied

Color must be in hex format, e.g. `#007AFF`

Xml attribute name: dimelo\_bottom\_sheet\_icons\_enabled\_color

Programmmatically: use `Customization.setBottomSheetIconsEnabledColor` method

### attachment Icon Button
Specify a drawable to use for the attachment icon

Programmmatically: use `Customization.setAttachmentIcon` method

### Bottom sheet disabled state icons color
Define the color the icons icons placed in the bottom sheet when they are disabled

Color must be in hex format, e.g. `#007AFF`

Xml attribute name: dimelo\_bottom\_sheet\_icons\_disabled\_color

Programmmatically: use `Customization.setBottomSheetIconsDisabledColor` method

### Bottom sheet disabled state icons color
Define the color the icons icons placed in the bottom sheet when they are disabled

Color must be in hex format, e.g. `#007AFF`

Xml attribute name: dimelo\_bottom\_sheet\_icons\_disabled\_color

Programmmatically: use `Customization.setBottomSheetIconsDisabledColor` method

### ActionBar background color
ActionBar color (ChatActiviy only)

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

	```
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

			```
			<activity android:name="com.dimelo.dimelosdk.main.ChatActivity"
                      tools:replace="android:theme"
                      android:theme="@style/your_theme">
			</activity>
			```

		* For AttachmentActivity

			```
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

### date TextColor
Text color for the date label.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_date\_color

Programmatically: set `Customization.dateTextColor` property.

### agent Name color
Text color for agent's name.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_agent\_name\_color

Programmatically: set `Customization.agentNameColor`  property

# Attributes < dimen />

### User Bubble padding

Padding of the user's message bubble

Xml attributes name:

- dimelo\_user\_message\_bubble\_left\_padding

- dimelo\_user\_message\_bubble\_right\_padding

- dimelo\_user\_message\_bubble\_top\_padding

- dimelo\_user\_message\_bubble\_bottom\_padding

Programmatically: set `Customization.userMessageBubblePadding` property

### Agent Bubble padding

Padding of the agent's message bubble

Xml attributes name:

- dimelo\_agent\_message\_bubble\_left\_padding

- dimelo\_agent\_message\_bubble\_right\_padding

- dimelo\_agent\_message\_bubble\_top\_padding

- dimelo\_agent\_message\_bubble\_bottom\_padding

Programmatically: set `Customization.agentMessageBubblePadding` property

### System Bubble padding

Padding of the system's message bubble

Xml attributes name:

- dimelo\_system\_message\_bubble\_left\_padding

- dimelo\_system\_message\_bubble\_right\_padding

- dimelo\_system\_message\_bubble\_top\_padding

- dimelo\_system\_message\_bubble\_bottom\_padding

Programmatically: set `Customization.systemMessageBubblePadding` property

### User Attachment Bubble padding

Padding of the user's attachment bubble

Xml attributes name:

- dimelo\_user\_attachment\_bubble\_left\_padding

- dimelo\_user\_attachment\_bubble\_right\_padding

- dimelo\_user\_attachment\_bubble\_top\_padding

- dimelo\_user\_attachment\_bubble\_bottom\_padding

Programmatically: set `Customization.userAttachmentBubblePadding` property

### Agent Attachment Bubble padding

Padding of the agent's attachment bubble

Xml attributes name:

- dimelo\_agent\_attachment\_bubble\_left\_padding

- dimelo\_agent\_attachment\_bubble\_right\_padding

- dimelo\_agent\_attachment\_bubble\_top\_padding

- dimelo\_agent\_attachment\_bubble\_bottom\_padding

Programmatically: set `Customization.agentAttachmentBubblePadding` property

### System Attachment Bubble padding

Padding of the system's attachment bubble

Xml attributes name:

- dimelo\_system\_attachment\_bubble\_left\_padding

- dimelo\_system\_attachment\_bubble\_right\_padding

- dimelo\_system\_attachment\_bubble\_top\_padding

- dimelo\_system\_attachment\_bubble\_bottom\_padding

Programmatically: set `Customization.systemAttachmentBubblePadding` property

# Typeface

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

### defaultSize
Set a global size to all the elements for which a text size can be set.

Programmatically: None.

Xml attribute name: dimen/dimelo_default_text_size
