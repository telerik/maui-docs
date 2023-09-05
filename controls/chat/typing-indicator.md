---
title: Typing Indicator
page_title: .NET MAUI Conversational UI Documentation - Typing Indicator
description: Learn more about typing indicator functionality of the Conversational UI
position: 8
slug: chat-typing-indicator
---

# .NET MAUI Chat Typing Indicator

The `TypingIndicator` functionality of the `RadChat` component allows you to indicate that other Chat participants are currently typing.

By default, the `TypingIndicator` is not visible. As soon as its `Authors` (or `ItemsSource`) collection is updated, it is displayed with a text message indicating the authors' names. It can also be displayed explicitly by setting the `IsTyping` and/or `IsVisible` properties to `true`.

The text message is built according to the count of authors like this:

* If the collection of `Authors` contains 1 item: "[Author name] is typing";
* If the authors are two: "[Author 1 name] and [Author 2 name] are typing";
* If the authors are three: "[Author 1 name], [Author 2 name] and [Author 3 name] are typing";
* If the authors are four or more: "[Author 1 name], [Author 2 name] and 2 others are typing";

When the `Authors` (or `ItemsSource`) collection is cleared, the `TypingIndicator` is hidden.

In addition, by setting the `Text` property of the indicator, the text message can be replaced with any other of your choice.

## Adding a Typing Indicator

To add a typing indicator, set the `TypingIndicator` property of the `RadChat` control:

<snippet id='chat-typingindicator-xaml' />
	
To display the typing indicator, use the `Authors` collection. You can use the `Authors` collection, which is of type `ObservableCollection<Author>` to show the participants who are currently typing. Here is a quick example:

<snippet id='chat-typingindicator-authors-code' />

The following images shows the results from the example above:

>caption `RadChat` with a typing indicator

![.NET MAUI Chat with typing indicator](images/chat-typing-indicator.png)

## See Also

- [Commands]({% slug chat-commands %})
- [Chat Items]({%slug chat-items-overview %})
- [MVVM Support]({%slug chat-mvvm-support %})
