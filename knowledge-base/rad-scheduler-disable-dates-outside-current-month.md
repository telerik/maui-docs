---
title: Disabling Past and Future Month Dates in RadScheduler for .NET MAUI
description: Learn how to prevent creating appointments for dates outside the current month in RadScheduler for .NET MAUI.
type: how-to
page_title: How to Disable Appointment Creation for Past and Future Month Dates in RadScheduler
slug: rad-scheduler-disable-dates-outside-current-month
tags: calendar, .net maui, radscheduler, disable dates, month view
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 7.1.0 | Telerik UI for .NET MAUI Scheduler | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

This article demonstrates how to prevent the creation of appointments for dates outside the current month.

This KB article also answers the following questions:
- How can I disable past and future dates in Scheduler for .NET MAUI?
- Is it possible to limit appointment creation to the current month in the Scheduler control?
- How do I prevent users from adding appointments to dates that are not in the current month in `RadScheduler`?

## Solution

To achieve the desired behavior of disabling dates outside the current month in `RadScheduler`, follow these steps:

1. Subscribe to the `MonthDayTapped` and `DialogOpening` events in your RadScheduler XAML code:

```xml
<telerik:RadScheduler x:Name="scheduler"
                      MonthDayTapped="scheduler_MonthDayTapped"
                      DialogOpening="scheduler_DialogOpening">
    <telerik:RadScheduler.ViewDefinitions>
        <telerik:MonthViewDefinition />
    </telerik:RadScheduler.ViewDefinitions>
</telerik:RadScheduler>
```

2. Implement the event handlers to cancel the dialog opening for dates outside the current month. This will effectively disable creating appointments for these dates:

```csharp
private bool allowAppointmentCreation = false;

private void scheduler_DialogOpening(object sender, SchedulerDialogOpeningEventArgs e)
{
    if (this.scheduler.ActiveViewDefinition is MonthViewDefinition)
    {
        e.Cancel = !this.allowAppointmentCreation;
    }
}

private void scheduler_MonthDayTapped(object sender, Telerik.Maui.Controls.Scheduler.TappedEventArgs<DateTime> e)
{
    var currentMonth = DateTime.Now.Month;
    var date = e.Data;

    if (date.Month == currentMonth)
    {
        this.allowAppointmentCreation = true;
        this.scheduler.CreateAppointmentWithDialog(new DateRange(date, date.AddHours(1)));
        this.allowAppointmentCreation = false;
    }
}
```

By setting the `allowAppointmentCreation` flag based on whether the tapped date is within the current month, you can control the opening of the appointment creation dialog. This solution ensures that users can only create appointments for dates within the current month.

## See Also

- [Scheduler Overview](https://docs.telerik.com/devtools/maui/controls/scheduler/overview)
- [Month View Definition](https://docs.telerik.com/devtools/maui/controls/scheduler/viewdefinitions/monthviewdefinition)
