---
title: Overview
page_title: .NET MAUI Conversational UI Documentation - ChatPicker Overview
description: Learn more about different pickers that RadChat control provides
position: 0
slug: chat-picker-overview
---

# ChatPicker Overview

The `RadChat` component offers different pickers allowing you to present the user a selection of choices either as a part of the conversation, or over the messages' view. 

Depending on the information that is presented and the choice that should be made, the pickers can be one of the types listed below. 

* `DatePicker`&mdash;Displays a Calendar to choose a date.
* `TimePicker`&mdash;Displays a clock view to choose a time.
* `ItemPicker`&mdash;Displays a list of suggestions the end user could choose from.
* `CardPicker`&mdash;Displays a list of cards with structured layout.

Each of these pickers is a part of the `RadChatPicker` control and is defined through the corresponding `PickerContext` property, namely `DatePickerContext`, `TimePickerContext`, `ItemPickerContext`, etc.
 
You can use `RadChatPicker` in three different ways:

* [Inline as a part of the conversation](#inline-as-part-of-the-conversation)–Through a `PickerItem` added to the Chat’s Items collection.
* [Inside the Chat but not as a part of the conversation](#inside-the-chat---not-part-of-the-conversation)–The picker is placed between the entry and the conversation–implemented through the Chat’s Picker property.
* As a separate Chat Picker control–Shown outside the `RadChat` control.

### Inline as Part of the Conversation

In this case, you need to create an item of type `PickerItem` that derives from the `ChatItem`. Set its `Context`, and add it to the `Items` collection of the Chat.

The following example demonstrates how to use the `RadChatPicker` inline as a part of the conversation:

<snippet id='chat-chatpicker-datepicker' />
	
When the user makes a selection, you can add a new `TextMessage` with the `SelectedDate` and remove the `PickerItem` from the conversation.

### Inside the Chat - Not Part of the Conversation

If you choose this approach, you need to create a `RadChatPicker` instance and set it to the `Picker` property of the Chat:

<snippet id='chat-pickeroverlay-xaml' />

Then, when you need to display any of the available pickers, you set the `Context` property of the `ChatPicker`. The next example shows how to achieve this with `DatePickerContext`:

<snippet id='chat-chatpicker-overlay-code' />
			
When the user selects a date, the `Context` is reset to `null` and a new `TextMessage` with the `SelectedDate` can be added to the conversation. The `IsVisible` property of the picker can also be set to `false`.

In the example above, `RadChatPicker` is used for immediate selection by setting its `IsOkButtonVisible` and `IsCancelButtonVisible` to false. You can also show **OK** and **Cancel** buttons and use the provided events/commands to handle the selection.
	
## See Also

- [DatePicker]({% slug chat-datepicker %})
- [TimePicker]({% slug chat-timepicker %})
- [ItemPicker]({% slug chat-itempicker %})
- [CardPicker]({% slug chat-cardpicker %})
