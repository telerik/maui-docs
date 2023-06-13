---
title: Commands
page_title: .NET MAUI Conversational UI Documentation - Commands
description: Learn how to use the exposed commands of the Telerik UI for .NET MAUI Chat
position: 7
slug: chat-commands
---

# .NET MAUI Chat Commands

The Telerik UI for .NET MAUI Chat allows you to attach commands that will be executed when certain actions such as `SendMessage` occur.

## Chat Commands

Take advantage of the `SendMessageCommand` that is triggered when the send-message button is clicked or when the user presses the `Enter` key on desktop platforms. The command is raised before the Chat auto-creates a `ChatItem` and adds it to the `Items` collection.

Here is an example on how to define a command in the ViewModel and bind the `SendMessageCommand` to it:

**1.** Add the command's `Execute` method.

<snippet id='chat-commands-executemethod' />

**2.** Define the `RadChat` component:

<snippet id='chat-commands-xaml' />

**3.** Add the ViewModel:

<snippet id='chat-commands-viewmodel' />

## See Also

- [MVVM Support]({% slug chat-mvvm-support%})
