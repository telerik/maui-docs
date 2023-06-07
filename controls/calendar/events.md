---
title: Events
page_title: .NET MAUI Calendar Documentation - Events
description: Check our &quot;Evenys&quot; documentation article for Telerik Calendar for .NET MAUI control.
position: 11
slug: calendar-events
---

# .NET MAUI Calendar Events

Calendar for .NET MAUI exposes the following events:

* `DisplayDateChanged`event is invoked when the current display date is changed. The `DisplayDateChanged` event handler receives two parameters:
	* The sender argument which is of type object, but can be cast to the RadCalendar type.
	* A `ValueChangedEventArgs&lt;DateTime&gt;` object which provides both old and new values of the `DisplayDate` property. The values are of type `DateTime`.

**Example for `DisplayDateChanged`:**

Calendar definition:

<snippet id='calendar-displaydate-event'/>

And the event handler:

<snippet id='calendar-displaydate-changed'/>


* `SelectionChanged` event is invoked when selection is performed. The `SelectionChanged` event handler receives two parameters
	* The `sender` which is the `RadCalendar` control.
	* `CalendarSelectionChangedEventArgs` provides the following properties:
		- `RemovedDates`&mdash;The dates that were deselected.
		- `AddedDates`&mdash;The dates that were selected.

**Example for `SelectionChanged`:**

Calendar definition:

<snippet id='calendar-selection-event'/>

And the event handler:

<snippet id='calendar-selection-changed-event'/>

## See Also

- [Navigation]({%slug calendar-navigation%})
- [Display modes]({%slug calendar-display-modes%})
- [Formatting]({%slug calendar-date-formatting%})
- [Selection modes]({%slug calendar-selection%})
- [Commands]({%slug calendar-commands%})
- [Templates]({%slug calendar-templates-overview%})
- [Styling]({%slug calendar-header-styling%})