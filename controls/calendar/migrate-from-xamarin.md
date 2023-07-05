---
title: Migrating from Xamarin
page_title: .NET MAUI Calendar Documentation - Migrate from Xamarin
description: Learn how to migrate you application from the Xamarin.Forms Calendar to the .NET MAUI Calendar control.
position: 20
slug: calendar-migrate-from-xamarin
---

# Migrate from Xamarin.Forms Calendar to .NET MAUI Calendar

The Telerik UI for .NET MAUI Calendar control has been designed and built from the ground up as a new control with a new API and significant improvements over its Xamarin counterpart.

In Telerik UI for Xamarin, the Calendar also includes scheduling, while the Telerik UI for .NET MAUI Calendar and Scheduler are different controls. As of today, the development of the Scheduler is planned. 

>note The Telerik UI for .NET MAUI Calendar control provides selection and does not manage appointments like the Telerik Xamarin Calendar does. The appointments will be part of the Telerik .NET MAUI Scheduler control.  

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

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
