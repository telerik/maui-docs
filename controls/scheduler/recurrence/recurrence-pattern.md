---
title: Recurrence Pattern
page_title: .NET MAUI Scheduler Documentation - Recurrence Pattern 
description: Learn more about the reccurence pattern option in Telerik UI for .NET MAUI Scheduler control.
position: 1
slug: scheduler-recurrence-pattern
---

# Recurrence Pattern

The Scheduler supports repeating appointments through the `RecurrenceRule` property of the `Appointment` class. In order to create a recurrence rule, you have to define a recurrence pattern, such as frequency, days of week, max occurrences, and other.

The `RecurrenceRule` property has a mandatory `Pattern` property of type `RecurrencePattern` which describes how the appointment occurrences will be created through various recurrence settings.

Check below a list of the properties exposed by the `RecurrencePattern` class:

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
- [Recurrence Overview]({%slug scheduler-recurrence-overview%})
- [Recurrence Rule]({%slug scheduler-recurrence-rule%})