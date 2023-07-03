---
title: MVVM Support 
page_title: .NET MAUI Conversational UI Documentation - MVVM Support
description: Learn how to utilize the MVVM pattern with RadChat control
position: 7
slug: chat-mvvm-support
---

# .NET MAUI Chat MVVM Support 

With the `RadChat` control, you can use the Model-View-ViewModel (MVVM) pattern. You can achieve this through the `ItemsSource` property that can be bound or set to a collection of data items that will be converted into Chat items.

The following example shows how to use `RadChat` in MVVM scenarios.

**1.** Create a sample class used to hold the needed information for the Chat items:

<snippet id='chat-features-mvvm-chatitem'/>

**2.** Create a ViewModel containing a collection of your `SimpleChatItem` items. You can also bind the Chat's `Author` property that represents the end user typing in the input field.

<snippet id='chat-features-mvvm-viewmodel'/>

**3.** Create a `Converter` class of type `IChatItemConverter` to convert the data items into Chat messages and the other way around:

<snippet id='chat-features-mvvm-converter'/>

**4.** Add the `RadChat` control to your page with previously defined `ItemsSource` and `ItemConverter` properties:

<snippet id='chat-features-mvvm-xaml' />
	
	
## See Also

- [Commands]({% slug chat-commands %})
- [ItemTemplateSelector] ({% slug chat-itemtemplate-selector %})