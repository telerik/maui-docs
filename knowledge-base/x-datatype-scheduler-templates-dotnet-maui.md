---
title: Using x:DataType in Scheduler Day/Week Templates in .NET MAUI
description: Learn what is the x:DataType for the Scheduler DayView and WeekView templates in .NET MAUI when using a custom appointment class.
type: how-to
page_title: How to Define x:DataType for Scheduler Templates in .NET MAUI
slug: x-datatype-scheduler-templates-dotnet-maui
tags: scheduler,.net maui,data binding,appointmentnode,appointmenttemplate
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.0 | Telerik UI for .NET MAUI Scheduler | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to use a custom appointment class with the Scheduler's DayView and WeekView templates in .NET MAUI. However, I am unsure of the correct `x:DataType` declaration for the `AppointmentTemplate`. When using custom properties in the appointment class, warnings appear, but the application still builds and runs correctly.

This knowledge base article also answers the following questions:
- How do I set the `x:DataType` for Scheduler templates?
- What is the `x:DataType` for `AppointmentTemplate` in .NET MAUI Scheduler?
- How to use a custom appointment class with Scheduler templates?

## Solution

To correctly set the `x:DataType` for the Scheduler's `AppointmentTemplate`, use the `AppointmentNode`. Below is an example of how to declare the `x:DataType` in XAML:

```xaml
<DataTemplate x:DataType="telerik:AppointmentNode">
    <!-- Template content goes here -->
</DataTemplate>
```

### Important Notes

- If using a custom appointment class that inherits from `Appointment`, warnings may appear for custom properties. These warnings do not affect the application's build or runtime behavior.

## See Also

- [Scheduler for .NET MAUI Documentation](https://docs.telerik.com/devtools/maui/controls/scheduler/overview)
- [Scheduler Appointment Templates Documentation](https://docs.telerik.com/devtools/maui/controls/scheduler/appointments/appointment-template) 
