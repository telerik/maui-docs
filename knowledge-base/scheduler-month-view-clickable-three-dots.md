---
title: Making the Three Dots in Scheduler Month View Clickable
description: Learn how to make the three dots clickable in the Scheduler Month View for small resolutions, allowing users to view and select events.
type: how-to
page_title: Enabling Clickable Three Dots in Scheduler Month View for Event Selection
meta_title: Clickable Three Dots in UI for .NET MAUI Scheduler Month View
slug: scheduler-month-view-clickable-three-dots
tags: scheduler, ui-for-dotnet-maui, events, monthdaytapped, commands, appointments
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.1.0 | Telerik UI for .NET MAUI Scheduler | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to make the three dots in the Scheduler Month View clickable, especially for small resolutions. Users should be able to interact with these dots to view and select events for a specific day. The goal is to either switch to the Day View of the selected date or display a pop-up/dialog listing the events for that day.

This knowledge base article also answers the following questions:
- How to handle the `MonthDayTapped` event in Scheduler?
- How to retrieve appointments for a specific day in the Scheduler Month View?
- How to display a list of events when the three dots are clicked?

## Solution

To make the three dots clickable and retrieve all appointments for a specific day, use the `MonthDayTapped` event or `MonthDayTapCommand`. Below is an example of using the `MonthDayTapped` event:

1. Define the Scheduler and bind the `MonthDayTapped` event.

```xaml
<telerik:RadScheduler x:Name="scheduler" 
                      MonthDayTapped="scheduler_MonthDayTapped"
                      AppointmentsSource="{Binding Appointments}">
    <telerik:RadScheduler.ViewDefinitions>
        <telerik:MonthViewDefinition />
    </telerik:RadScheduler.ViewDefinitions>
</telerik:RadScheduler>
```

2. Create a `ViewModel` with a list of appointments. This will serve as the data source.

```csharp
public class ViewModel
{
    public ViewModel()
    {
        var date = DateTime.Today;
        this.Appointments = new ObservableCollection<Appointment>
        {
            new Appointment {
                Subject = "Meeting",
                Start = date.AddHours(10),
                End = date.AddHours(11)
            },
            new Appointment {
                Subject = "Lunch",
                Start = date.AddHours(12).AddMinutes(30),
                End = date.AddHours(14)
            },
            new Appointment {
                Subject = "Elle Birthday",
                Start = date,
                End = date.AddHours(11),
                IsAllDay = true
            }
        };
    }

    public ObservableCollection<Appointment> Appointments { get; set; }
}
```

3. Handle the `MonthDayTapped` event to retrieve appointments for the selected day and display them in a dialog.

```csharp
public partial class MainPage : ContentPage
{
    ViewModel vm;

    public MainPage()
    {
        InitializeComponent();
        this.vm = new ViewModel();
        this.BindingContext = this.vm;
    }

    private void scheduler_MonthDayTapped(object sender, TappedEventArgs<DateTime> e)
    {
        var items = this.vm.Appointments;
        var appointmentsFromDay = new List<Appointment>();
        foreach (var item in items)
        {
            if (item.Start.Day == e.Data.Day)
            {
                appointmentsFromDay.Add(item);
            }
        }
        App.Current.MainPage.DisplayAlert("", appointmentsFromDay.Count + " Appointments", "OK");
    }
}
```

Modify the logic further based on your specific requirements.

## See Also

- [Scheduler Events](https://www.telerik.com/maui-ui/documentation/controls/scheduler/events)
- [Scheduler Commands](https://www.telerik.com/maui-ui/documentation/controls/scheduler/commands)
- [UI for .NET MAUI Scheduler Overview](https://www.telerik.com/maui-ui/documentation/controls/scheduler/overview)
