---
title: Message
page_title: .NET MAUI Chat Documentation - Message Styling
description: Learn how to style the outgoing and incoming messages in the Telerik UI for .NET MAUI Chat control.
position: 6
tags: .net maui, telerik .net maui, ui for .net maui, chat, style
slug: chat-message-styling
---

# .NET MAUI Chat Message Styling

Any change in the appearance of the `RadChat` components depends on the referenced styles. 

The default templates contain a `RadBorder` control (used to achieve the rounded edges), an Image control (used for the avatar of the single and first message), and a Label for the text message itself.

To customize the different parts of the control, you can use the following implicit styles:

* `Image`&mdash;Represents the avatar image of the message.

```XAML
<Style TargetType="Image">

</Style>
```

* `ChatIncomingSingleTextMessageView`&mdash;Represents a view that visualizes a single incoming text message, i.e. when the number of consecutive messages from the same author is one.
* `ChatIncomingFirstTextMessageView`&mdash;Represents a view that visualizes an incoming text message that is the first in a series of messages from the same author.
* `ChatIncomingMiddleTextMessageView`&mdash;Represents a view that visualizes an incoming text message that is in the middle of a series of messages from the same author.
* `ChatIncomingLastTextMessageView`&mdash;Represents a view that visualizes an incoming text message that is the last in a series of messages from the same author.

```XAML
<Style TargetType="telerik:ChatIncomingSingleTextMessageView">
    <Setter Property="BorderStyle">
        <Setter.Value>
            <Style TargetType="telerik:RadBorder">
            </Style>
        </Setter.Value>
    </Setter>
    <Setter Property="LabelStyle">
		<Setter.Value>
			<Style TargetType="Label">
			</Style>
		</Setter.Value>
	</Setter>
</Style>
```

* `ChatOutgoingSingleTextMessageView`&mdash;Represents a view that visualizes a single outgoing text message, i.e. when the number of consecutive messages from the same author is one.
* `ChatOutgoingFirstTextMessageView`&mdash;Represents a view that visualizes an outgoing text message that is the first in a series of messages from the same author.
* `ChatOutgoingMiddleTextMessageView`&mdash;Represents a view that visualizes an outgoing text message that is in the middle of a series of messages from the same author.
* `ChatOutgoingLastTextMessageView`&mdash;Represents a view that visualizes an outgoing text message that is the last in a series of messages from the same author.

```XAML
<Style TargetType="telerik:ChatOutgoingSingleTextMessageView">
    <Setter Property="BorderStyle">
        <Setter.Value>
            <Style TargetType="telerik:RadBorder">
            </Style>
        </Setter.Value>
    </Setter>
    <Setter Property="LabelStyle">
		<Setter.Value>
			<Style TargetType="Label">
			</Style>
		</Setter.Value>
	</Setter>
</Style>
```

To define background color of the Chat set the `BackgroundColor`(`Color`) property.

## See Also

- [Commands]({% slug chat-commands %})
- [Chat Items]({%slug chat-items-overview %})
- [MVVM Support]({%slug chat-mvvm-support %})