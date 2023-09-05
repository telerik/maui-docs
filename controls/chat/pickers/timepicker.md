---
title: TimePicker
page_title: .NET MAUI Conversational UI Documentation - Chat TimePicker
description: Learn more about ChatPicker control and its TimePicker context
position: 2
slug: chat-timepicker
---

# .NET MAUI Chat TimePicker 

The `RadChatPicker` control provides a `TimePickerContext` that can be used to display a clock view to choose a time.

`TimePickerContext` exposes the following properties that you can use to adjust the clock items:

* `SelectedValue`&mdash;Defines the currently selected time.
* `StartTime`&mdash;A property of type `TimeSpan` that represents the starting time of the clock's items.
* `EndTime`&mdash;A property of type `TimeSpan` that corresponds to the time of the last clock item.
* `TimeInterval`&mdash;A property of type `TimeSpan` that defines the step between the clock's items. Te default value is 1 hour.

Here is a quick example on how to use the TimePicker in `RadChat`:

<snippet id='chat-chatpicker-timepicker' />
	
>caption Chat with TimePicker

![.NET MAUI Chat Message](images/chat-time-picker.png)

## See Also

- [ChatPicker]({% slug chat-picker-overview %})
- [ItemPicker]({% slug chat-itempicker %})
- [CardPicker]({% slug chat-cardpicker %})