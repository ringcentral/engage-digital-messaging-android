Dimelo Chat Customization
==========================

Dimelo chat is customizable either from Android resource folder (XML) or programmatically

This file shows a list of attributes you can override in order to customize the chat.

Attributes < string />
----

### Toolbar Title String
Title of the conversation window (ChatActiviy only)

Xml attribute name: dimelo\_toolbar\_title

Programmatically: None

Attributes < bool />
----
### Toolbar Title display
Specify if the title of the toolbar must be displayed (ChatActiviy only)

Xml attribute name: dimelo\_toolbar\_display\_title

Programmatically: None

Attributes < drawable />
----
### Toolbar Navigation Icon drawable
Specify a drawable to use for the navigation icon of the toolbar(ChatActiviy only)

Xml attribute name: dimelo\_navigation\_icon

Programmatically: None


### Toolbar Background drawable
Specify a drawable to use for the toolbar. (ChatActiviy only)  
The drawable can be tinted with dimelo\_toolbar\_background\_drawable\_tint.

Xml attribute name: dimelo\_toolbar\_background\_drawable

Programmatically: None

Attributes < color />
----

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

Typeface
----

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
