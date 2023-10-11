---
title: Recurrence Pattern
page_title: .NET MAUI Scheduler Documentation - Recurrence Pattern 
description: Learn more about the reccurence pattern option in Telerik UI for .NET MAUI Scheduler control.
position: 0
slug: recurrence-pattern
---

# Recurrence Pattern

The `RadScheduler` includes support for recurring events on daily, weekly, monthly and yearly basis. To When an appointment is promoted into a recurring event its `RecurrenceRule` is set with correct `RecurrencePattern`.

Here are the exposed properties exposed by the `RecurrencePatter` class:

* `Frequency`&mdash;Defines the frequency. Its values are predefined in the `RecurrenceFrequency`enumeration, which exposes the following values: None, Secondly, Minutely, Hourly, Daily, Weekly, Monthly, Yearly. 
* `DaysOfMonth`&mdash;Defines the days of a month.
* `DayOrdinal`&mdash;Defines the day ordinal.
* `DaysOfWeekMask`&mdash;Defines the days of week mask.
* `HoursOfDay` &mdash;Defines the hours of a day.
*  `MinutesOfHour`&mdash;Defines the minutes of an hour. 
* `FirstDayOfWeek` &mdash; Defines the day on which the week starts.
* `Interval` &mdash;Defines the interval.
* `MaxOccurences`&mdash;Defines the limit for the number of occurrences.
* `MonthOfYear` &mdash;Defines the month in the year.
* `RecursUntil`&mdash; Defines the end date of the appointment occurrences.

## See Also

- [Appointments]({% slug appointments-overview %})
- [Recurrence Overview]({%slug recurrence-overview})
- [Recurrence Rule]({%slug recurrence-rule})