---
title: Commands
page_title: .NET MAUI Conversational UI Documentation - Commands
description: Learn how to use the exposed commands of the Telerik UI for .NET MAUI Conversational UI
position: 7
slug: chat-commands
---

# .NET MAUI RadChat Commands

Telerik UI for .NET MAUI RadChat allows you to attach commands that will be executed when certain actions such as SendMessage occur.

## Chat Commands

Take advantage of the `SendMessageCommand` that is triggered by two actions when the send-message button is clicked. The command is raised before the Chat auto-creates a ChatItem and adds it to the Items.

Here is an example on how to define a command in the ViewModel and bind the `SendMessageCommand` to it:

And the command Execute method:

Definition of RadChat components:



## See Also

- [MVVM Support]({% slug chat-mvvm-support%})
