---
title: Events
page_title: .NET MAUI Calendar Documentation - Events
description: Learn about the events that the Telerik UI for .NET MAUI Calendar control exposes and find out how to use them to configure the UI component.
position: 11
slug: calendar-events
---

# .NET MAUI Calendar Events

The Telerik UI for .NET MAUI Calendar component exposes a set of events that users trigger through interaction. You can handle these events and customize the configuration of the UI component.

The Calendar for .NET MAUI exposes the [`DisplayDateChanged`](#displaydatechanged) and the [`SelectionChanged`](#selectionchanged) events.

## DisplayDateChanged

The `DisplayDateChanged` event is invoked when the current display date is changed. The `DisplayDateChanged` event handler receives two parameters:

* The sender argument, which is of type `object`, but can be cast to the `RadCalendar` type.
* A `ValueChangedEventArgs<DateTime>` object, which provides both the old and new values of the `DisplayDate` property. The values are of type `DateTime`.

The following example demonstrates how to use the `DisplayDateChanged` event:

**1.** Define the Calendar:

<snippet id='calendar-displaydate-event'/>

**2.** And the event handler:

<snippet id='calendar-displaydate-changed'/>

## SelectionChanged

The `SelectionChanged` event is invoked when the selection changes. The `SelectionChanged` event handler receives two parameters:
* The `sender`, which is the `RadCalendar` control.
* The `CalendarSelectionChangedEventArgs` object, which provides the following properties:
	* `RemovedDates`&mdash;The deselected dates.
	* `AddedDates`&mdash;The selected dates.

The following example demonstrates how to use the `SelectionChanged` event:

**1.** Define the Calendar:

<snippet id='calendar-selection-event'/>

**2.** And the event handler:

<snippet id='calendar-selection-changed-event'/>

## See Also

- [Navigation Between the Different Views]({%slug calendar-navigation%})
- [Specify the Formatting]({%slug calendar-date-formatting%})
- [Selection modes]({%slug calendar-selection%})
- [Use the exposed Commands]({%slug calendar-commands%})
- [Define Templates]({%slug calendar-templates-overview%})
- [Calendar Header Styling]({%slug calendar-header-styling%})
