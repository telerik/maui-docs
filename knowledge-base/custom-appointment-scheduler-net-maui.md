---
title: Creating a Custom Appointment Model in Scheduler for .NET MAUI
description: Learn how to extend the appointment model in Scheduler for .NET MAUI with additional properties for enhanced data handling.
type: how-to
page_title: How to Extend the Appointment Model with Custom Properties in .NET MAUI Scheduler
slug: custom-appointment-model-scheduler-net-maui
tags: scheduler, .net maui, custom model, appointment, data binding
res_type: kb
ticketid: 1662472
---

## Environment

<table>
<tbody>
<tr>
<td>Product</td>
<td>Scheduler for .NET MAUI</td>
</tr>
</tbody>
</table>

## Description

When working with the [Scheduler](https://docs.telerik.com/devtools/maui/controls/scheduler/overview) in .NET MAUI, there might be scenarios requiring additional data to be stored within appointments. This necessitates creating a custom appointment model class that extends the capabilities of the default appointment model.

This KB article also answers the following questions:
- How can I add extra properties to the Scheduler's appointments?
- Is it possible to customize the appointment model in .NET MAUI Scheduler?
- How to display additional appointment data in .NET MAUI Scheduler?

## Solution

To include extra properties in the appointment model, implement a custom class that inherits from `Telerik.Maui.Controls.Scheduler.Appointment`. Override the `Copy` and `CopyFrom` methods for proper data handling. Additionally, utilize a custom `AppointmentTemplate` to display the new properties in the Scheduler.

### Step 1: Create a Custom Appointment Class

Define a custom class that extends `Appointment` and add your custom properties. Override the `Copy` and `CopyFrom` methods to ensure the custom properties are correctly handled during internal operations.

```csharp
public class MyCustomAppointment : Appointment
{
    private string token;

    public string Token
    {
        get => this.token;
        set => this.UpdateValue(ref this.token, value);
    }

    public override IAppointment Copy()
    {
        var myAppt = new MyCustomAppointment();
        myAppt.CopyFrom(this);
        return myAppt;
    }

    public override void CopyFrom(IAppointment other)
    {
        var myAppt = other as MyCustomAppointment;
        if (myAppt != null)
        {
            this.Token = myAppt.Token;
        }

        base.CopyFrom(other);
    }
}
```

### Step 2: Customize the Appointment Template

To display the custom properties in the Scheduler, define a `DataTemplate` incorporating the new properties and assign it to the `AppointmentTemplate` property of the Scheduler.

```xml
<DataTemplate x:Key="MyCustomAppointmentTemplate">
    <telerik:RadBorder CornerRadius="4"
                    IsClippedToBounds="True"
                    BackgroundColor="#D2C6E6">
        <Grid>
            <BoxView WidthRequest="4"
                    BackgroundColor="#8660C5"
                    HorizontalOptions="Start" />
            <VerticalStackLayout  Margin="6, 0, 4, 0" Spacing="4">
                <Label Text="{Binding Occurrence.Appointment.Subject}"
                    TextColor="Black" />
                <Label Text="{Binding Occurrence.Appointment.Token}"
                    TextColor="Red" />
            </VerticalStackLayout>
        </Grid>
    </telerik:RadBorder>
</DataTemplate>

<telerik:RadScheduler x:Name="scheduler"
            AppointmentsSource="{Binding Appointments}"
            AppointmentTemplate="{StaticResource MyCustomAppointmentTemplate}">
    <telerik:RadScheduler.ViewDefinitions>
        <telerik:DayViewDefinition />
        <telerik:WeekViewDefinition Title="Work Week" IsWeekendVisible="False" />
        <telerik:MonthViewDefinition />
    </telerik:RadScheduler.ViewDefinitions>
</telerik:RadScheduler>
```

### Step 3: Customize the Appointment Dialog (Optional)

To enable users to edit the custom property through the `EditAppointmentDialog`, modify its `ControlTemplate`. Refer to the [Controls Samples](https://docs.telerik.com/devtools/maui/demos-and-sample-apps/controls-showcase-app) app for an example of dialog customization.

## See Also

- [Scheduler Overview](https://docs.telerik.com/devtools/maui/controls/scheduler/overview)
- [Appointment Template Documentation](https://docs.telerik.com/devtools/maui/controls/scheduler/appointments/appointment-template)
- [Controls Samples App - Scheduler Dialog Customization](https://docs.telerik.com/devtools/maui/demos-and-sample-apps/controls-showcase-app)
