---
title: Recurrence Rule
page_title: .NET MAUI Scheduler Documentation - Recurrence Rule
description: Learn more about the reccurence rule option in Telerik UI for .NET MAUI Scheduler control.
position: 2
slug: scheduler-recurrence-rule
---

# Recurrence Rule

The Scheduler supports repeating appointments through the `RecurrenceRule` property of the `Appointment` class. In order to create a recurrence rule, you have to define a recurrence pattern, such as frequency, days of week, max occurrences, and other.

The `RecurrenceRule` property has a mandatory `Pattern` property of type `RecurrencePattern` which describes how the appointment occurrences will be created through various recurrence settings. For detailed information on how to create the recurrence pattern go to [Recurrence Pattern]({%slug scheduler-recurrence-pattern%}) topic.


The main methods exposed by the `RecurrenceRule` class:

* `Copy()(type IRecurrenceRule)`&mdash;Defines the new instance of the `RecurrenceRule`.
* `CopyFrom()`&mdash;Defines the pattern properties that are duplicate of the specified `RecurrencePattern` object in the `RecurrencePattern` object that calls this method.

## Exceptions 

The `RecurrenceRule` class exposes an exceptions method, which allows you to get or set all exception occurrences associated with the current rule.

* `CreateExceptionAppointment`&mdash;Defines a new `IAppointment` instance that will hold the properties of an exception occurrence.

## See Also

- [Appointments]({% slug appointments-overview %})
- [Recurrence Overview]({%slug scheduler-recurrence-overview%})
- [Recurrence Pattern]({%slug scheduler-recurrence-pattern %})
