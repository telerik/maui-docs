---
title: Migrating from Xamarin
page_title: .NET MAUI Calendar Documentation - Migrate from Xamarin
description: "Learn how to migrate from Xamarin.Forms Calendar to .NET MAUI Calendar control."
position: 20
slug: calendar-migrate-from-xamarin
---

# Migrate from Xamarin.Forms Calendar to .NET MAUI Calendar

Overall, Telerik .NET MAUI Calendar control is a complete new control with new API and improvements. 

In Telerik UI for Xamarin the Calendar control has also a scheduling, while in Telerik .NET MAUI Calendar and Scheduler are separate controls. The Scheduler is with status planned. 

>note The Telerik .NET MAUI Calendar control provides selection and does not manage apointments like the Telerik Xmaarin Calendar does. The appointments will be part of the Telerik .NET MAUI Scheduler control.  

Compare API changes in Xamarin.Forms Calendar and .NET MAUI Calendar are described in the tables below:

## Migrate the Namespaces

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
