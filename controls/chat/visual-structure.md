---
title: Visual Structure
page_title: .NET MAUI Conversational UI Documentation - Visual Structure
description: Learn more about the visual structure of the Conversational UI
position: 1
slug: chat-visual-structure
---

# .NET MAUI Chat Visual Structure

The visual structure of the .NET MAUI Chat represents the anatomy of the UI component. Being familiar with the visual elements of the Chat allows you to quickly find the information required to configure them.

The following image shows the anatomy of the Chat.

![.NET MAUI Chat Visual Structure](images/chat-visualstructure.png)

## Displayed Elements

- `Author`&mdash;Represents the current user who sends messages using the Chat UI. This instance determines the alignment of the messages—incoming messages are placed on the left, outgoing messages—on the right.
- `Items`&mdash;Contains all the chat items included in the conversation, such text messages, picker items, and so on. For more details on the available Chat items, see the [Chat Items]({%slug chat-items-overview %}) topic.
- `Message`&mdash;Defines the current message typed into the input field.
- `Send Button`&mdash;Defines the button used to send messages.
- `Picker`&mdash;Defines the Chat Picker that is shown either as overlay over the messages’ view or inline as part of the conversation and could display different pickers to provide the end user with a selection of choices. See the [Chat Picker topic]({% slug chat-picker-overview %}) for more details.
- `Typing Indicator`&mdash;Defines the indicator which is shown when one of the chat authors is typing.

## See Also

- [Commands]({% slug chat-commands %})
- [Chat Items]({%slug chat-items-overview %})
- [MVVM Support]({%slug chat-mvvm-support %})
