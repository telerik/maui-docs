---
title: MVVM Support 
page_title: .NET MAUI Conversational UI Documentation - MVVM Support
description: Learn how to utilize the MVVM pattern with RadChat control
position: 7
slug: chat-mvvm-support
---

# .NET MAUI RadChat MVVM Support 

With `RadChat` control you could easily utilize the Model-View-ViewModel (MVVM) pattern. This could be achieved through the `ItemsSource` property that can be bound/set to a collection of any data items that should be then converted into chat items.

This help article will demonstrate how to use `RadChat` in MVVM scenarios.

Create a sample class used to hold the needed information for the chat items:

<snippet id='chat-features-mvvm-chatitem'/>

Create a ViewModel containing a collection of your SimpleChatItem items. You could also bind the Chat's Author property that represents the end user typing in the input field.

<snippet id='chat-features-mvvm-viewmodel'/>

Create a Converter class of type IChatItemConverter in order to convert the data items into chat messages and vice versa:

<snippet id='chat-features-mvvm-converter'/>

Add the RadChat control to your page with previously defined ItemsSource and ItemConverter properties:

<snippet id='chat-features-mvvm-xaml' />
	
#### Figure 1: RadChat in MVVM setup

![MVVM Support](images/)
	
## See Also

- [Commands]({% slug chat-commands %})
- [ItemTemplateSelector] ({% slug chat-itemtemplate-selector %})