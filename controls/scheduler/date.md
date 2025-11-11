---
title: Date Properties
page_title: .NET MAUI Scheduler Documentation - Date Properties
description: Learn more about the date properties of the Telerik UI for .NET MAUI Scheduler control.
position: 3
slug: scheduler-date
---

# .NET MAUI Scheduler Date Properties

The .NET MAUI Scheduler exposes several date-related properties that you can use to work with dates in the active view.

* `MinDate` (`DateTime`)&mdash;Defines the minimum date that can be navigated to in the scheduler. This property restricts backward navigation and prevents displaying dates earlier than the specified minimum. The default value is `2000, 1, 1`.
* `MaxDate` (`DateTime`)&mdash;Defines the maximum date that can be navigated to in the scheduler. This property restricts forward navigation and prevents displaying dates later than the specified maximum. The default value is `2099, 12, 31`.
* `CurrentDate` (`DateTime`)&mdash;Defines the primary date that determines the visible range of the scheduler. The actual visible range depends on the active view definition. For example, in `WeekView`, this date determines which week is displayed; in `MonthView`, which month is shown. The default value is today's date.

## See Also

- [Views]({% slug scheduler-views-overview %})
- [Month View]({%slug scheduler-month-view%})
- [MultiDay View]({%slug scheduler-multiday-view%})