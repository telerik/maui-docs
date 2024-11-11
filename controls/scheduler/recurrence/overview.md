---
title: Overview
page_title: .NET MAUI Scheduler Documentation - Recurrence Overview
description: Learn more about the reccurence option in Telerik UI for .NET MAUI Scheduler control.
position: 0
slug: scheduler-recurrence-overview
---

# Overview

The Scheduler for .NET MAUI lets you configure repeating appointments. The user has the ability to apply recurring scheduling patterns such as daily, weekly, and monthly, or set a range of recurrence from date to date. The flexible rule mechanism covers the most common recurrence scenarios. Furthermore, you also have the option to handle the exceptions from this rule.

To support the recurrence behavior, the `Appointment` class exposes `RecurrenceRule` property. The `RecurrenceRule` class is the engine for creating and evaluating recurrence rules. It has a mandatory `Pattern` property of type `RecurrencePattern` which defines the frequency, days of week, max occurrences, and more, of the recurrent appointment. Through the `RecurrenceRule` property you can also define exception appointments.
  
The example below shows a simple recurrent appointment which occurs every week day and has overall 10 occurrences:

```C#
var appointment = new Appointment()
{
    Subject = "Daily appointment",
    Start = date.AddHours(11),
    End = date.AddHours(11).AddMinutes(30)
};

var pattern = new RecurrencePattern()
{
    Frequency = RecurrenceFrequency.Daily,
    DaysOfWeekMask = RecurrenceDays.WeekDays,
    MaxOccurrences = 10
};

appointment.RecurrenceRule = new RecurrenceRule(pattern);
```

If you want to dive deeper into the recurrence feature of the .NET MAUI Scheduler, check out the following topics:

* [Recurrence Pattern]({%slug scheduler-recurrence-pattern %})
* [Recurrence Rule]({%slug scheduler-recurrence-rule %})

## See Also

- [Appointments]({% slug appointments-overview %})
- [Recurrence Pattern]({%slug scheduler-recurrence-pattern %})
- [Recurrence Rule]({%slug scheduler-recurrence-rule %})
