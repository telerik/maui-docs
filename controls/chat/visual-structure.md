---
title: Visual Structure
page_title: .NET MAUI Conversational UI Documentation - Visual Structure
description: Learn more about the visual structure of the Conversational UI
position: 1
slug: chat-visual-structure
---

# .NET MAUI Chat Visual Structure

The visual structure of the .NET MAUI Chat represents the anatomy of the UI component. Being familiar with the visual elements of the Chat allows you to quickly find the information required to configure them.

The following image shows the anatomy of the Chat. ataGrid visual structure documentation.

![.NET MAUI Chat Visual Structure](images/chat-visualstructure.png)

## Displayed Elements

- `Author` &mdash; Represents the current user who sends messages using the Chat UI. Determines the alignment of the messages: incoming messages are placed on the left, outgoing messages on the right. (Marker near the user avatar.)
- `Items` &mdash; Contains all the chat items included in the conversation, such as text messages, picker items, and more. (Markers near both message bubbles.)
- `Message` &mdash; Defines the current message typed into the input field. (Marker inside the text box showing "Type a message...")
- `Send Button` &mdash; Button used to send messages. (Marker on the paper-plane icon.)
- `More Button` &mdash; Button used to open additional options, such as attaching files or images. (Marker on the plus icon.)
- `Input Field` &mdash; Area where users type their messages. (Marker outlining the input container.)
- `SpeechToTextButton` &mdash; Button used to convert speech to text. (Marker on the microphone icon.)

## See Also

- [Commands]({% slug chat-commands %})
- [Chat Items]({%slug chat-items-overview %})
- [MVVM Support]({%slug chat-mvvm-support %})
