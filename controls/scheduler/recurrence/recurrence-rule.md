---
title: Recurrence Rule
page_title: .NET MAUI Scheduler Documentation - Recurrence Rule
description: Learn more about the reccurence rule option in Telerik UI for .NET MAUI Scheduler control.
position: 
slug: recurrence-rule
---

# Recurrence Rule

`RadScheduler` includes support for recurring events on daily, weekly, monthly and yearly basis. hen an appointment is promoted into a recurring event its `RecurrenceRule` is set with correct `RecurrencePattern`.

The main methods exposed by the `RecurrenceRule` class:

* `Copy()(type IRecurrenceRule)`&mdash;Defines the new instance of the `RecurrenceRule`.
* `CopyFrom()`&mdash;Defines the pattern properties that are duplicate of the specified `RecurrencePattern` object in the `RecurrencePattern` object that calls this method.

## Exceptions 

The `RecurrenceRule` class exposes an exceptions method, which allows you to get or set all exception occurrences associated with the current rule.

* `CreateExceptionAppointment`&mdash;Defines a new `IAppointment` instance that will hold the properties of an exception occurrence.


## See Also

- 
- 
- 
- 