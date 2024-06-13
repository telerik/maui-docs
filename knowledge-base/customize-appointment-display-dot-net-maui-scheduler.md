---
title: Customizing Appointments in Telerik UI for .NET MAUI Scheduler
description: Learn how to customize the appointment display in the Telerik UI for .NET MAUI Scheduler to show a dot next to the appointment text instead of a background color.
type: how-to
page_title: How to Customize Appointments in .NET MAUI Scheduler
slug: customize-appointment-display-dot-net-maui-scheduler
tags: calendar, .net maui, scheduler, appointment, template, customization
res_type: kb
ticketid: 1654745
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 7.0.0 | Telerik UI for .NET MAUI Scheduler | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

In migrating from Telerik UI for Xamarin to Telerik UI for .NET MAUI, I need to display a small colored dot next to the appointment in the month view in the [Scheduler]({%slug scheduler-overview%}), rather than using a background color.

This KB article also answers the following questions:
- How can I use the AppointmentTemplate to customize appointments in Telerik UI for .NET MAUI Scheduler?
- Is it possible to display a dot next to an appointment in the month view of the Scheduler?
- How to customize the appearance of appointments in Telerik UI for .NET MAUI Scheduler?

## Solution

To customize the appointment display in Telerik UI for .NET MAUI Scheduler to show a colored dot instead of a background color, you can utilize the `AppointmentTemplate`. Here's an example using `RadBorder` to create the dot alongside the appointment text.

1. Define the custom appointment data template in your page's resources:

```xml
<ContentPage.Resources>
    <ResourceDictionary>
        <local:CustomAppointmentDataTemplate x:Key="CustomAppointmentDataTemplate">
            <local:CustomAppointmentDataTemplate.AllDayAppointmentTemplate>
                <DataTemplate>
                    <HorizontalStackLayout>
                        <telerik:RadBorder WidthRequest="10"
                                           HeightRequest="10" 
                                           CornerRadius="5" 
                                           BackgroundColor="Aqua" />
                            <Label Text="{Binding Occurrence.Appointment.Subject}"
                           TextColor="Black"  Margin="6, 0, 4, 0"
                           VerticalTextAlignment="Center" />
                        </HorizontalStackLayout>
                </DataTemplate>
            </local:CustomAppointmentDataTemplate.AllDayAppointmentTemplate>
            <local:CustomAppointmentDataTemplate.AppointmentTemplate>
                <DataTemplate>
                    <HorizontalStackLayout>
                        <telerik:RadBorder WidthRequest="10" HeightRequest="10" CornerRadius="5"
                         BackgroundColor="#8660C5"
                         HorizontalOptions="Start" />
                        <Label Text="{Binding Occurrence.Appointment.Subject}"
                               VerticalTextAlignment="Center"
                       TextColor="Black" 
                       Margin="6, 0, 4, 0" />
                    </HorizontalStackLayout>
                </DataTemplate>
            </local:CustomAppointmentDataTemplate.AppointmentTemplate>
        </local:CustomAppointmentDataTemplate>
    </ResourceDictionary>
</ContentPage.Resources>
```

2. Apply the custom template to the `RadScheduler`:

```xml
<telerik:RadScheduler x:Name="scheduler" 
                      AppointmentsSource="{Binding Appointments}"
                      AppointmentTemplate="{StaticResource CustomAppointmentDataTemplate}">
    <telerik:RadScheduler.ViewDefinitions>
        <telerik:MonthViewDefinition />
    </telerik:RadScheduler.ViewDefinitions>
</telerik:RadScheduler>
```

3. Implement the `CustomAppointmentDataTemplate` class and the ViewModel in your code-behind or view model file:

```csharp
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        this.BindingContext = new ViewModel();
    }
}

public class CustomAppointmentDataTemplate : DataTemplateSelector
{
    public DataTemplate AllDayAppointmentTemplate { get; set; }
    public DataTemplate AppointmentTemplate { get; set; }

    protected override DataTemplate OnSelectTemplate(object item, BindableObject container)
    {
        var appointment = (item as AppointmentNode).Occurrence.Appointment;
        if (appointment.IsAllDay || (appointment.End - appointment.Start).TotalDays > 1)
        {
            return this.AllDayAppointmentTemplate;
        }

        return this.AppointmentTemplate;
    }
}

public class ViewModel
{
    public ObservableCollection<Appointment> Appointments { get; set; }

    public ViewModel()
    {
        var date = DateTime.Today;
        this.Appointments = new ObservableCollection<Appointment>
        {
            new Appointment {
                Subject = "Meeting with Tom",
                Start = date.AddHours(10),
                End = date.AddHours(11)
            },
            new Appointment {
                Subject = "Lunch with Sara",
                Start = date.AddHours(12).AddMinutes(30),
                End = date.AddHours(14)
            },
            new Appointment {
                Subject = "Elle Birthday",
                Start = date,
                End = date.AddHours(11),
                IsAllDay = true
            },
            new Appointment {
                Subject = "Football Game",
                Start = date.AddDays(2).AddHours(15),
                End = date.AddDays(2).AddHours(17)
            }
        };
    }
}
```

This approach allows you to customize the appearance of appointments in Telerik UI for .NET MAUI Scheduler to include a colored dot, similar to the previous Xamarin implementation.

## See Also

- [Scheduler Documentation]({%slug scheduler-overview%})
- [AppointmentTemplate in Telerik UI for .NET MAUI Scheduler]({%slug scheduler-appointment-template%})
