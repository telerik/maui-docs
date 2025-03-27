---
title: Defining Non-Working Hours in Scheduler for .NET MAUI
description: Learn how to display non-working hours in the Telerik Scheduler for .NET MAUI across DayView, WeekView, and MultiDayView.
type: how-to
page_title: Displaying Non-Working Hours in Scheduler Views for .NET MAUI
slug: scheduler-net-maui-non-working-hours
tags: scheduler, .net maui, non-working hours, dayview, weekview, multidateview, special slots
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.0.0 | Scheduler for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

In transitioning from Xamarin Calendar and Scheduler to Telerik Scheduler for .NET MAUI, it's essential to know how to define and display non-working hours in DayView, WeekView, and MultiDayView modes. 

This knowledge base article also answers the following questions:
- How can I mark non-working hours in the Telerik Scheduler for .NET MAUI?
- What approach should I use to display special slots indicating non-working hours in different Scheduler views?
- How do I configure the Scheduler to show non-working hours using the `SpecialSlots` feature?

## Solution

To display non-working hours in the Telerik Scheduler for .NET MAUI, leverage the [`SpecialSlots`](https://docs.telerik.com/devtools/maui/controls/scheduler/specialslots/overview) feature. This solution involves configuring the Scheduler in the XAML, setting up the `ViewModel` to define non-working hours. Follow the steps below to achieve this.

**1.** Define the Scheduler in XAML with the `SpecialSlotsSource` property for each view to bind to the non-working hours collection.

```xaml
<Grid>
    <telerik:RadScheduler AppointmentsSource="{Binding Appointments}">
        <telerik:RadScheduler.ViewDefinitions>
            <telerik:WeekViewDefinition SpecialSlotsSource="{Binding NonWorkingHours}" />
            <telerik:WeekViewDefinition Title="Work Week"
                                        IsWeekendVisible="False"
                                        SpecialSlotsSource="{Binding NonWorkingHours}" />
            <telerik:MultidayViewDefinition VisibleDays="3"
                                            Title="3 Day"
                                            SpecialSlotsSource="{Binding NonWorkingHours}" />
            <telerik:DayViewDefinition SpecialSlotsSource="{Binding NonWorkingHours}" />
        </telerik:RadScheduler.ViewDefinitions>
    </telerik:RadScheduler>
</Grid>
```

**2.** Define the `ViewModel` to include a collection of appointments and non-working hours.
The non-working hours are defined as special slots with a recurrence pattern to repeat weekly.

```C#
public class ViewModel : NotifyPropertyChangedBase
{
    public ViewModel()
    {
        this.Appointments = new ObservableCollection<Appointment>();
        var now = DateTime.Now;
        // Appointments are added here...
        
        this.NonWorkingHours = new ObservableCollection<Slot>(); 

        DateTime start = new DateTime(2010, 1, 1, 8, 0, 0); 
        DateTime end = new DateTime(2010, 1, 1, 18, 0, 0); 
        this.NonWorkingHours.Add(new Slot(end, start.AddDays(1))
        {
            RecurrencePattern = new RecurrencePattern(null, RecurrenceDays.Monday | RecurrenceDays.Tuesday | RecurrenceDays.Wednesday | RecurrenceDays.Thursday, RecurrenceFrequency.Weekly, 1, null, null) 
        }); 
        
        this.NonWorkingHours.Add(new Slot(end, start.AddDays(3))
        { 
            RecurrencePattern = new RecurrencePattern(null, RecurrenceDays.Friday, RecurrenceFrequency.Weekly, 1, null, null) 
        }); 
    }

    public ObservableCollection<Appointment> Appointments { get; set; }
    public ObservableCollection<Slot> NonWorkingHours { get; set; } 
}
```

**3.** Set the binding context of your page to the `ViewModel` to ensure the Scheduler is bound to the appropriate data.

```C#
this.BindingContext = new ViewModel();
```

By following these steps, the Telerik Scheduler for .NET MAUI will display non-working hours as specified in the `ViewModel`, across day view, week view, and multi day view definitions. This approach effectively utilizes the SpecialSlots feature to highlight non-working hours, enhancing the scheduler's functionality and user experience.

## See Also

- [Scheduler Special Slots Overview](https://docs.telerik.com/devtools/maui/controls/scheduler/specialslots/overview)
- [Scheduler for .NET MAUI Documentation](https://docs.telerik.com/devtools/maui/controls/scheduler/overview)