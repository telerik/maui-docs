---
title: Commands
page_title: .NET MAUI Conversational UI Documentation - Commands
description: Learn how to use the exposed commands of the Telerik UI for .NET MAUI Chat
position: 7
slug: chat-commands
---

# .NET MAUI Chat Commands

The Telerik UI for .NET MAUI Chat allows you to attach commands that will be executed when certain actions occur.

## Commands Related to the Chat Input Area:

* `SendMessageCommand` (`ICommand`)&mdash;Defines the command that is executed when the send button is clicked or the `Enter` key is pressed. 

## Commands Related to Attachments

* `` ()&mdash;

## Example with SendMessageCommand

Here is an example on how to define a command in the ViewModel and bind the `SendMessageCommand` to it:

**1.** Add the command's `Execute` method.

<snippet id='chat-commands-executemethod' />

**2.** Define the `RadChat` component:

<snippet id='chat-commands-xaml' />

**3.** Add the ViewModel:

<snippet id='chat-commands-viewmodel' />

## See Also

- [MVVM Support]({% slug chat-mvvm-support%})
- [Chat Items]({%slug chat-items-overview %})
