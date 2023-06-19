---
title: Chat Messages
page_title: .NET MAUI Conversational UI Documentation - Chat Messages
description: Learn more about the Chat Message unit in RadChat
position: 1
slug: chat-items-messages
---

# Chat Messages 

`ChatMessage` is the basic message unit in `RadChat`. It contains information about the `Author` of the message as well as any additional data about the message.

The Author property is of type `Telerik.Maui.Controls.Chat.Author` and exposes the following properties:

* `Name`&mdash;Author name;
* `Avatar`&mdash;Image related to the author, displayed in the Chat UI;
* `Data`&mdash;You can use it to preserve additional information about the author;

By default, when the end user types in the text box and confirms the message, it is set to the to Chat's `Message` property. In addition, the `SendMessage` event is fired each time a new message is about to be added to the Chat UI. It allows you to modify the message itself.

## Text Message

The `TextMessage` is intended to be used for sending a simple string type message. It derives from `ChatMessage` and provides an additional `Text` property which holds the string message. 

### Adding a message

The following example demonstrates how to create a sample `TextMessage`:

```C#
var bot = new Author() { Name = "bot", Avatar = "SampleAvatar.png" };
chat.Items.Add(new TextMessage { Author = bot, Text = "Hi." });
chat.Items.Add(new TextMessage { Author = bot, Text = "This is a message." });
```

## See Also

- [Time Break]({%slug chat-items-timebreak %})
- [PickerItem]({%slug chat-picker-overview %})
- [MVVM Support]({% slug chat-mvvm-support %})
