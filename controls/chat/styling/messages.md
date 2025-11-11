---
title: Message
page_title: .NET MAUI Chat Documentation - Message Styling
description: Learn how to style the outgoing and incoming messages in the Telerik UI for .NET MAUI Chat control.
position: 6
tags: .net maui, telerik .net maui, ui for .net maui, chat, style
slug: chat-message-styling
---

# .NET MAUI Chat Message Styling

Any change in the appearance of the `RadChat` components depends on the referenced styles. The default templates contain a `RadBorder` control (used to achieve the rounded edges), an Image control (used for the avatar of the single and first message), and a Label for the text message itself.

To customize the different parts of the control, you can use the following built-in styles:

- `MessageImageStyle`(target type `Image`)&mdash;Defines the style referred to the send button image.

- `OutgoingMessageImageStyle` (target type `Image`)&mdash;Defines the style of the outgoing message image.

- `IncomingBorderStyle` (target type `RadBorder`)&mdash;Defines the style of the incoming message border.

- `OutgoingBorderStyle` (target type `RadBorder`)&mdash;Defines the style of the outgoing message border.

- `DefaultLabelStyle` (target type `Label`)&mdash;Defines the default label style.

- `OutgoingLabelStyle` (target type `Label`)&mdash;Defines the style of the label of the outgoing message.

In addition, the following properties set the background of the Chat:

* `BackgroundColor`(`Color`)&mdash;Defines the background color of the Chat control.
* `InputAreaBackgroundColor`(`Color`)&mdash;Defines the bacgkround color of the area that the input elements (entry and button) reside.

## See Also

- [Commands]({% slug chat-commands %})
- [Chat Items]({%slug chat-items-overview %})
- [MVVM Support]({%slug chat-mvvm-support %})