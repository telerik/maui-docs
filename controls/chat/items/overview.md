---
title: Overview
page_title: .NET MAUI Conversational UI Documentation - RadChat Items Overview
description: Learn more about the ChatItem collection in the RadChat control
position: 0
slug: chat-items-overview
---

# Chat Items 

The `RadChat` control works with a collection of `ChatItem` objects. The control provides different Chat Items that you can use, such as the basic `TextMessage` and the `PickerItems` used to display various pickers (item, date, and time picker) and predefined cards (defined through a card picker).

This section covers the specific details of the different Chat Items provided by `RadChat`:

* [Message]({%slug chat-items-messages %})—The basic message unit in RadChat; apart from the text of the message itself, each `TextMessage` instance contains information about the Author of the message as well as any additional data.
* [Time Break]({%slug chat-items-timebreak %})—Used to encapsulate messages in a conversation by a certain condition such as read/unread, time intervals, or any other condition. It visualizes as a dividing line across the messages board with a text message attached to it.
* [PickerItem]({%slug chat-picker-overview %})—A special `ChatItem` type which contains a `RadChatPicker` control used for providing a selection to the end user. Depending on the information that is presented and the choices the user can make, the pickers can be one of the following types:
	* `DatePicker`&mdash;Displays a Calendar to choose a date.
    * `TimePicker`&mdash;Displays a clock view to choose a time.
    * `ItemPicker`&mdash;Displays a list of suggestions the end user could choose from.
    * `CardPicker`&mdash;Displays a list of cards with structured layout.

> Additionally, you can create your own Chat Items with custom item templates and add them to the `Items` collection of the control. For more details, see the [MVVM Support]({% slug chat-mvvm-support %}) and [`ItemTemplateSelector`]({% slug chat-itemtemplate-selector %}) topics.

## See Also

- [Messages]({%slug chat-items-messages %})
- [Time Break]({%slug chat-items-timebreak %})
- [PickerItem]({%slug chat-picker-overview %})
- [MVVM Support]({% slug chat-mvvm-support %})
- [ItemTemplateSelector] ({% slug chat-itemtemplate-selector %})
