---
title: ItemPicker
page_title: .NET MAUI Conversational UI Documentation | Chat ItemPicker
description: Learn more about ChatPicker control and its ItemPicker context
position: 3
slug: chat-itempicker
---

# .NET MAUI Chat ItemPicker 

The `RadChatPicker` control provides an `ItemPickerContext` that can be used to display a list of options the end user could choose from.

`ItemPickerContext` exposes the following properties you could use to provide a list of possible options to the user:

* `ItemsSource`&mdash;defines the data source used to generate the content of the ItemPicker control;
* `SelectionMode`&mdash;defines whether users are allowed to select one or many items out of the provided ItemsSource;
* `SelectedItems`&mdash;defines the currently selected items;
* `SelectedItem`&mdash;defines the last selected item;

Here is a quick example on how to user ItemPicker:

<snippet id='chat-chatpicker-itempicker' />
	
#### Figure 1: Chat with ItemPicker

![Chat Message](images/)

## See Also

- [ChatPicker]({% slug chat-picker-overview %})
- [DatePicker]({% slug chat-datepicker %})
- [TimePicker]({% slug chat-timepicker %})
- [CardPicker]({% slug chat-cardpicker %})