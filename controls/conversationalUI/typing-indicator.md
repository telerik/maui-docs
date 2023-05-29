---
title: Typing Indicator
page_title: .NET MAUI Conversational UI Documentation - Typing Indicator
description: "Learn more about typing indicator functionality of the Conversational UI."
position: 8
slug: chat-typing-indicator
---

# .NET MAUI Conversational UI Typing Indicator

The `TypingIndicator` functionality of Conversational UI can be used to indicate that a participant (or participants) is currently typing.

By default, the `TypingIndicator` is not visible. As soon as its Authors (or ItemsSource) collection is updated, it is displayed with a text message indicating the authors’ names. 

The text message is built according to the count of authors like this:

* If the collection of Authors contains 1 item: “[Author name] is typing”;
* If there are two authors: “[Author1 name] and [Author2 name] are typing”;
* In case of three authors: “[Author1 name], [Author2 name] and [Author3 name] are typing”;
* In case of more authors: [Author1 name], [Author2 name] and 2 others are typing”;

When the Authors (or `ItemsSource`) collection is cleared, the `TypingIndicator` is hidden.

In addition, by setting `Text` property the text message could be replaced with any other of your choice.

#### Adding a TypingIndicator

Add a typing indicator just set TypingIndicator property of RadChat control:

<snippet id='chat-typingindicator-xaml' />
	
Two ways to display the typing indicator:

#### Using Authors collection:

You can use directly `Authors` collection which is of type `ObservableCollection<Author>` to show the participants who are currently typing. Here is a quick example:

<snippet id='chat-typingindicator-authors-code' />

And the result is:

