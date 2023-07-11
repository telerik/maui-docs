---
title: Migrating from Xamarin
page_title: .NET MAUI Calendar Documentation - Migrate from Xamarin
description: Learn how to migrate you application from the Xamarin.Forms Calendar to the .NET MAUI Calendar control.
position: 20
slug: calendar-migrate-from-xamarin
---

# Migrating from Xamarin.Forms Calendar to .NET MAUI Calendar

The Telerik UI for .NET MAUI Calendar control has been designed and built from the ground up as a new control with a new API and significant improvements over its Xamarin counterpart.

When you plan to migrate from Xamarin to .NET MAUI, consider the following differences in the feature set of the Calendar control:
* Unlike the Xamarin Calendar, the .NET MAUI Calendar allows three selection modes—single, multiple, and range.
* Unlike the Xamarin Calendar, the .NET MAUI Calendar does not manage appointments. In Telerik UI for .NET MAUI, appointments will be handled by the .NET MAUI Scheduler control, which is planned for the R3 2023 release.

The tables in the following sections list the differences between the APIs of the Xamarin.Forms Calendar and .NET MAUI Calendar.

## Namespaces Differences

| Control | Control name | C# Namespace| XAML Namespcace |
| --------------- | --------------- | --------------- | --------------------------------------------------- |
| Xamarin Calendar | `RadCalendar` | xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input" | using Telerik.XamarinForms.Input; |
| .NET MAUI Calendar | `RadCalendar` |  xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## API Changes

| Xamarin Calendar | .NET MAUI Calendar |
| ------------- | --------------- |
| `ViewMode`(enum of type `CalendarViewMode`) | `DisplayMode`(enum of type `CalendarDisplayMode`) |
| Styling the cells, view modes, using custom renderers for styling | New Styling API or the different parts of the calendar and different view modes |
| API for Appointments/Scheduling UI | No Scheduler in Telerik .NET MAUI Calendar - Scheduler will be a separate control |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
