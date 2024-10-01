---
title: Migrating from Xamarin
page_title: Migrating the Calendar from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin Calendar to the Telerik UI for .NET MAUI Calendar by updating the namespaces, the incompatible NuGet packages and API.
tags: dot net maui, .net maui vs xamarin, maui vs xamarin, net maui vs xamarin, migration, xamarin.forms
position: 100
previous_url: /controls/calendar/migrate-from-xamarin
slug: calendar-migrate-from-xamarin
---

# Migrating the Calendar from Xamarin.Forms to .NET MAUI

The Telerik UI for .NET MAUI Calendar control has been designed and built from the ground up as a new control with a new API and significant improvements over its Xamarin counterpart.

When you plan to migrate from Xamarin to .NET MAUI, consider the following differences in the feature set of the Calendar control:
* Unlike the Xamarin Calendar, the .NET MAUI Calendar allows three selection modes—single, multiple, and range.
* Unlike the Xamarin Calendar, the .NET MAUI Calendar does not manage appointments. In Telerik UI for .NET MAUI, appointments are handled by the [.NET MAUI Scheduler control]({%slug scheduler-overview%}).

The tables in the following sections list the differences between the APIs of the Xamarin.Forms Calendar and .NET MAUI Calendar.

## Namespaces Differences

When migrating the Calendar from Xamarin to .NET MAUI, consider the following differences in the namespaces:

| Control | Control name | C# Namespace | XAML Namespcace |
| --------------- | --------------- | --------------- | --------------------------------------------------- |
| Xamarin Calendar | `RadCalendar` | xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input" | using Telerik.XamarinForms.Input; |
| .NET MAUI Calendar | `RadCalendar` |  xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## API Differences

When migrating the Calendar from Xamarin to .NET MAUI, consider the following differences in the API:

| Xamarin Calendar | .NET MAUI Calendar |
| ------------- | --------------- |
| `ViewMode`(enum of type `CalendarViewMode`) | `DisplayMode`(enum of type `CalendarDisplayMode`) |
| Styling the cells and the different view modes (DayView, MultiDay, AgendaView) requires custom renderers. | Styling the distinct parts of the calendar and its view modes is handled by the new Styling API. |
| Provides an API for appointments (Scheduling UI). | Does not provide an API for appointments. For scheduling appointments, use the Telerik UI for [.NET MAUI Scheduler]({%slug scheduler-overview%}) control.  |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug sampleapps-overview %})
* [.NET MAUI Calendar Product Page](https://www.telerik.com/maui-ui/calendar)
* [.NET MAUI Calendar Forum Page](https://www.telerik.com/forums/maui?tagId=2057)
