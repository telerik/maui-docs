---
title: Migrating from Xamarin
page_title: Migrating the Calendar from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin Calendar to the Telerik UI for .NET MAUI Calendar, including namespace and API differences.
components: ["calendar"]
tags: dot net maui, .net maui vs xamarin, maui vs xamarin, net maui vs xamarin, migration, xamarin.forms
position: 100
previous_url: /controls/calendar/migrate-from-xamarin
slug: calendar-migrate-from-xamarin
---

# Migrating the Calendar from Xamarin.Forms to .NET MAUI

Progress® Telerik® UI for .NET MAUI provides a new Calendar control with a new API and significant improvements over its Xamarin counterpart.

When you migrate from Xamarin.Forms to .NET MAUI, consider these Calendar feature differences:
* Unlike the Xamarin Calendar, the .NET MAUI Calendar allows three selection modes—single, multiple, and range.
* Unlike the Xamarin Calendar, the .NET MAUI Calendar does not manage appointments. In Telerik UI for .NET MAUI, appointments are handled by the [.NET MAUI Scheduler control]({%slug scheduler-overview%}).

The tables in the following sections list the differences between the APIs of the Xamarin.Forms Calendar and .NET MAUI Calendar.

## Migrating the Namespaces

Update the namespaces when you migrate the Calendar from Xamarin.Forms to .NET MAUI:

| Control | Control name | XAML Namespace | C# Namespace |
| --------------- | --------------- | --------------- | --------------------------------------------------- |
| Xamarin Calendar | `RadCalendar` | `xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input"` | `using Telerik.XamarinForms.Input;` |
| .NET MAUI Calendar | `RadCalendar` | `xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"` | `using Telerik.Maui.Controls;` |

## Migrating the API

Update the API references when you migrate the Calendar from Xamarin.Forms to .NET MAUI:

| Xamarin Calendar | .NET MAUI Calendar |
| ------------- | --------------- |
| `ViewMode` (enum of type `CalendarViewMode`) | `DisplayMode` (enum of type `CalendarDisplayMode`) |
| Styling the cells and the different view modes (DayView, MultiDay, AgendaView) requires custom renderers. | Style the distinct parts of the Calendar and its view modes with the new Styling API. |
| Provides an API for appointments (Scheduling UI). | Does not provide an API for appointments. For scheduling appointments, use the Telerik UI for [.NET MAUI Scheduler]({%slug scheduler-overview%}) control.  |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug sampleapps-overview %})
* [.NET MAUI Calendar Product Page](https://www.telerik.com/maui-ui/calendar)
* [.NET MAUI Calendar Forum Page](https://www.telerik.com/forums/maui?tagId=2057)
