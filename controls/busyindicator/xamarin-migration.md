---
title: Migrating from Xamarin
page_title: Migrating the BusyIndicator from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin BusyIndicator to the Telerik UI for .NET MAUI BusyIndicator by updating the namespaces, the incompatible NuGet packages and API.
tags: maui, dotnet maui, telerik maui, migration, xamarin.forms
position: 100
slug: busyindicator-xamarin-migration
---

# Migrating the BusyIndicator from Xamarin.Forms to .NET MAUI

Telerik .NET MAUI BusyIndicator control preserves the same API as Xamarin.Forms BusyIndicator with a few changes and improvements.

The tables in the following sections list the differences between the APIs of the Xamarin.Forms BusyIndicator and .NET MAUI BusyIndicator.

## Namespaces Differences

When migrating the BusyIndicator from Xamarin to .NET MAUI, consider the following differences in the namespaces:

| Control | Control name | XAML Namespace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin BusyIndicator | `RadBusyIndicator` | xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.XamarinForms.Primitives" | using Telerik.XamarinForms.Primitives; |
| .NET MAUI BusyIndicator | `RadBusyIndicator` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
* [.NET MAUI Barcode Product Page](https://www.telerik.com/maui-ui/barcode)
* [.NET MAUI Barcode Forum Page](https://www.telerik.com/forums/maui?tagId=1780)
