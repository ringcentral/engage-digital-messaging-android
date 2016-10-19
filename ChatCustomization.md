Dimelo Chat Customization
==========================

Dimelo chat is customizable either from Android resource folder (XML) or programmatically

This file shows a list of attributes you can override in order to customize the chat.

</br>
Attributes < string />
----

### Toolbar Title String
Title of the conversation window (ChatActiviy only)

Xml attribute name: dimelo\_toolbar\_title

Programmatically: None

</br>
Attributes < bool />
----
### Toolbar Title display
Specify if the title of the toolbar must be displayed (ChatActiviy only)

Xml attribute name: dimelo\_toolbar\_display\_title

Programmatically: None

</br>
Attributes < drawable />
----
### Toolbar Navigation Icon drawable
Specify a drawable to use for the navigation icon of the toolbar(ChatActivity only)

Xml attribute name: dimelo\_navigation\_icon

Programmatically: None


### Toolbar Background drawable
Specify a drawable to use for the toolbar. (ChatActiviy only)  
The drawable can be tinted with dimelo\_toolbar\_background\_drawable\_tint.

Xml attribute name: dimelo\_toolbar\_background\_drawable

Programmatically: None

</br>
Attributes < color />
----

### Toolbar Background drawable tint
Specify a tint for the drawable used as a background for the toolbar.(ChatActiviy only)

Xml attribute name: dimelo\_toolbar\_background\_drawable\_tint

Programmatically: None

</br>
### Toolbar Background color
Background color of toolbar (ChatActiviy only)

Xml attribute name: dimelo\_toolbar\_background\_color

Programmatically: None

</br>
### InputBar background color
Background color for the input bar

Color must be in hex format, e.g. `#007AFF`.
Xml attribute name: dimelo\_inputbar\_background\_color

Programmatically: set `Customization.inputbarBackgroundColor` property

</br>
### Send Button disabled color
Define the color the send button when no text is written and no attachment is selected.

Color must be in hex format, e.g. `#007AFF`

Xml attribute name: dimelo\_send\_button\_disabled\_color

Programmmatically: use `Customization.setSendButtonDisabledColor` method

</br>
### Bottom sheet enabled state icons color
Define the color the icons icons placed in the bottom sheet when they are enabled

Color must be in hex format, e.g. `#007AFF`

Xml attribute name: dimelo\_bottom\_sheet\_icons\_enabled\_color

Programmmatically: use `Customization.setBottomSheetIconsEnabledColor` method

</br>
### Bottom sheet disabled state icons color
Define the color the icons icons placed in the bottom sheet when they are disabled

Color must be in hex format, e.g. `#007AFF`

Xml attribute name: dimelo\_bottom\_sheet\_icons\_disabled\_color

Programmmatically: use `Customization.setBottomSheetIconsDisabledColor` method

</br>
### ActionBar background color
ActionBar color (ChatActiviy only)

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_toolbar\_background\_color

Programmatically: None

</br>
### chat background color
Background color of the chat.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_background\_color

Programmatically: set `Customization.backgroundColor` property

</br>
### user message TextColor
Foreground color for user's message text.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_user\_message\_text\_color

Programmatically: set `Customization.userMessageTextColor` property

</br>
### agent message TextColor
Foreground color for agent's message text.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_agent\_message\_text\_color

Programmatically: set `Customization.agentMessageTextColor` property

</br>
### system message TextColor
Foreground color for system's message text.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_system\_message\_text\_color

Programmatically: set `Customization.systemMessageTextColor` property

</br>
### user message BackgroundColor
Background color for user message bubbles.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_user\_bubble\_color

Programmatically: set this property by calling `Customization.setUserMessageBubbleDrawable` method.

</br>
### agent message BackgroundColor
Background color for agent message bubbles.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_agent\_bubble\_color

Programmatically: set this property by calling `Customization.setAgentMessageBubbleDrawable` method.

</br>
### system message BackgroundColor
Background color for system message bubbles.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_system\_bubble\_color

Programmatically: set this property by calling `Customization.setSystemMessageBubbleDrawable` method.

</br>
### user attachment bubbles BackgroundColor
Background color for user attachment bubbles.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_user\_attachment\_bubble\_color

Programmatically: set this property by calling `Customization.setUserAttachmentBubbleDrawable` method.

</br>
### agent attachment bubbles BackgroundColor
Background color for agent attachment bubbles.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_agent\_attachment\_bubble\_color

Programmatically: set this property by calling `Customization.setAgentAttachmentBubbleDrawable` method.

</br>
### date TextColor
Text color for the date label.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_date\_color

Programmatically: set `Customization.dateTextColor` property.

</br>
### agent Name color
Text color for agent's name.

Color must be in hex format, e.g. `#007AFF`.

Xml attribute name: dimelo\_agent\_name\_color

Programmatically: set `Customization.agentNameColor`  property

Attributes < dimen /> 
----

### User Bubble padding

Padding of the user's message bubble

Xml attributes name:

- dimelo\_user\_message\_bubble\_left\_padding

- dimelo\_user\_message\_bubble\_right\_padding

- dimelo\_user\_message\_bubble\_top\_padding

- dimelo\_user\_message\_bubble\_bottom\_padding

Programmatically: set `Customization.userMessageBubblePadding` property

</br>
### Agent Bubble padding

Padding of the agent's message bubble

Xml attributes name:

- dimelo\_agent\_message\_bubble\_left\_padding

- dimelo\_agent\_message\_bubble\_right\_padding

- dimelo\_agent\_message\_bubble\_top\_padding

- dimelo\_agent\_message\_bubble\_bottom\_padding

Programmatically: set `Customization.agentMessageBubblePadding` property

</br>
### System Bubble padding

Padding of the system's message bubble

Xml attributes name:

- dimelo\_system\_message\_bubble\_left\_padding

- dimelo\_system\_message\_bubble\_right\_padding

- dimelo\_system\_message\_bubble\_top\_padding

- dimelo\_system\_message\_bubble\_bottom\_padding

Programmatically: set `Customization.systemMessageBubblePadding` property


</br>
### User Attachment Bubble padding

Padding of the user's attachment bubble

Xml attributes name:

- dimelo\_user\_attachment\_bubble\_left\_padding

- dimelo\_user\_attachment\_bubble\_right\_padding

- dimelo\_user\_attachment\_bubble\_top\_padding

- dimelo\_user\_attachment\_bubble\_bottom\_padding

Programmatically: set `Customization.userAttachmentBubblePadding` property

</br>
### Agent Attachment Bubble padding

Padding of the agent's attachment bubble

Xml attributes name:

- dimelo\_agent\_attachment\_bubble\_left\_padding

- dimelo\_agent\_attachment\_bubble\_right\_padding

- dimelo\_agent\_attachment\_bubble\_top\_padding

- dimelo\_agent\_attachment\_bubble\_bottom\_padding

Programmatically: set `Customization.agentAttachmentBubblePadding` property

</br>
### System Attachment Bubble padding

Padding of the system's attachment bubble

Xml attributes name:

- dimelo\_system\_attachment\_bubble\_left\_padding

- dimelo\_system\_attachment\_bubble\_right\_padding

- dimelo\_system\_attachment\_bubble\_top\_padding

- dimelo\_system\_attachment\_bubble\_bottom\_padding

Programmatically: set `Customization.systemAttachmentBubblePadding` property


</br>
Typeface
----
### messageFont
Font for user and agent messages.

Programmatically: set `Customization.messageFont` property

Xml attribute name: None

</br>
### systemMessageFont
Font for system messages.

Programmatically: set `Customization.systemMessageFont` property

Xml attribute name: None

</br>
### dateFont
Font for the date label.

Programmatically: set `Customization.dateFont` property

Xml attribute name: None

</br>
### agentNameFont
Font for agent's name.

Programmatically: set `Customization.agentNameFont` property

Xml attribute name: None


</br>
Text Size
----
### messageTextSize
TextSize for user and agent messages.

Programmatically: set `Customization.messageTextSize` property

Xml attribute name: dimen/dimelo_message_text_size

</br>
### systemMessageTextSize
TextSize for system messages.

Programmatically: set `Customization.systemMessageTextSize` property

Xml attribute name: dimen/dimelo_system_message_text_size

</br>
### DateTextSize
TextSize for date label.

Programmatically: set `Customization.dateTextSize` property

Xml attribute name: dimen/dimelo_date_text_size

</br>
### agentNameTextSize
TextSize for agent name label.

Programmatically: set `Customization.agentNameTextSize` property

Xml attribute name: dimen/dimelo_agent_name_text_size

</br>
### messageFieldTextSize
TextSize for the message input.

Programmatically: set `Customization.messageFieldTextSize` property

Xml attribute name: dimen/dimelo_message_field_text_size

</br>
### defaultSize
Set a global size to all the elements for which a text size can be set.

Programmatically: None.

Xml attribute name: dimen/dimelo_default_text_size
