---
title: TimePicker
page_title: .NET MAUI Conversational UI Documentation - Chat TimePicker
description: Learn more about ChatPicker control and its TimePicker context
position: 2
slug: chat-timepicker
---

# .NET MAUI Chat TimePicker 

The `RadChatPicker` control provides a `TimePickerContext` that can be used to display a clock view to choose a time.

`TimePickerContext` exposes the following properties you could use to adjust the clock items:

* `SelectedValue`&mdash;defines the currently selected time
* `StartTime`&mdash;it is of type TimeSpan and represents the starting time of the clock's items
* `EndTime`&mdash;it is of type TimeSpan and corresponds to the time of the last clock item
* `TimeInterval`&mdash;it is also of type TimeSpan and defines the step between the clock's items. Default value is 1 hour

Here is a quick example on how to user TimePicker in RadChat:

<snippet id='chat-chatpicker-timepicker' />
	
#### Figure 1: Chat with TimePicker

![Chat Message](images/)

## See Also

- [ChatPicker]({% slug chat-picker-overview %})
- [ItemPicker]({% slug chat-itempicker %})
- [CardPicker]({% slug chat-cardpicker %})