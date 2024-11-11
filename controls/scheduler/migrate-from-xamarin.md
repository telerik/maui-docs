---
title: Migrating from Xamarin
page_title: .NET MAUI Scheduler Documentation - Migrate from Xamarin
description: Learn how to migrate from Xamarin.Forms Calendar & Scheduling to .NET MAUI Scheduler control.
position: 30
slug: scheduler-migrate-from-xamarin
---

# Migrate from Xamarin.Forms Calendar & Scheduling to .NET MAUI Scheduler

The Telerik UI for .NET MAUI Scheduler control has been designed and built from the ground up as a new control with a new API and significant improvements over its Xamarin counterpart.

If you need only a Calendar control for date selection, consider using [Telerik .NET MAUI Calendar]({%slug calendar-overview%}). In case you need a scheduling component for appointments management, Telerik UI for .NET MAUI Scheduler control is the way to go.

The tables in the following sections list the differences between the APIs of the Xamarin.Forms Calendar & Scheduling and .NET MAUI Scheduler.

## Namespaces Differences

|Control | Xamarin Calendar & Scheduling | .NET MAUI Scheduler |
| -------- | ------------- | ------------- |
| Control Name | `RadCalendar` | `RadScheduler` |
| C# Namespace |  using Telerik.XamarinForms.Input; | using Telerik.Maui.Controls; |
| XAML Namespace | xmlns:telerik="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input" | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" |


## API Differences

When migrating the Xamarin Calendar & Scheduling, consider the following differences in the API:

| Xamarin Calendar & Scheduling | .NET MAUI Scheduler |
| ------------- | ------------- |
| Available views - Day, Week, MultiDay, Month, Agenda and Year |Available views - Day, Week, MultiDay and Month |
| `ViewMode` | `ActiveViewDefinition`, `ActiveViewDefinitionIndex` |
| View configuration properties, such as `DayStartTime`, `DayEndTime` and `IsCurrentTimeIndicatorVisible` are defined through `DayViewSettings`, `MultiDayViewSettings` and `AgendaViewSettings` | View configuration properties, such as `DayStartTime`, `DayEndTime`, `IsCurrentTimeIndicatorVisible` are set directly to the `ViewDefinition` |
| Single, Multiple and Range selection | Available in .NET MAUI Calendar | 
| `Appointment` class with Title, StartDate, EndDate, Detail, Color, IsAllDay, RecurrenceRule | `Appointment` class with Subject, Start, End, Body, IsAllDay, RecurrenceRule |
| Add Appointment Button | N/A |
| Scheduling UIs | N/A |
| `SpecialSlot` class with StartDate, EndDate, IsReadOnly, RecurrencePattern | `Slot` class with Start, End, IsReadOnly, RecurrencePattern, TimeZone|
| `ScrollTimeIntoView`, `ScrollAppointmentIntoView` | `ScrollIntoView` |
| Commands - `CellTap`, `AppointmentTap`, `TimeSlotTap`| `AppointmentTapCommand`,`AppointmentDoubleTapCommand`,`SlotTapCommand`, `SlotDoubleTapCommand`, `MonthDayTapCommand`, `MonthDayDoubleTapCommand`, `IncreaseVisibleRangeCommand`, `DecreaseVisibleRangeCommand`, `TodayCommand` |
| Styling the cells and the different view modes (DayView, MultiDay, AgendaView) requires custom renderers| Styling the distinct parts of the Scheduler and its views is handled by the new Styling API. |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug sampleapps-overview %})
