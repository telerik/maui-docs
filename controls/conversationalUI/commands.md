---
title: Commands
page_title: .NET MAUI Conversational UI Documentation - Commands
description: Learn how to use the exposed commands of the Telerik UI for .NET MAUI Chat
position: 7
slug: chat-commands
---

# .NET MAUI Chat Commands

Telerik UI for .NET MAUI RadChat allows you to attach commands that will be executed when certain actions such as SendMessage occur.

## Chat Commands

Take advantage of the `SendMessageCommand` that is triggered by two actions when the send-message button is clicked. The command is raised before the Chat auto-creates a ChatItem and adds it to the Items.

Here is an example on how to define a command in the ViewModel and bind the `SendMessageCommand` to it:

And the command Execute method:

<snippet id='chat-commands-executemethod' />

Definition of RadChat components:

<snippet id='chat-commands-xaml' />

Add ViewModel:

<snippet id='chat-commands-viewmodel' />

## See Also

- [MVVM Support]({% slug chat-mvvm-support%})
