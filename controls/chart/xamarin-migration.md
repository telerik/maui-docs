---
title: Migrating from Xamarin
page_title: Migrating the Chart from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin Chart to the Telerik UI for .NET MAUI Chart by updating the namespaces, the incompatible NuGet packages and API.
tags: dot net maui, .net maui vs xamarin, maui vs xamarin, net maui vs xamarin, migration, xamarin.forms
position: 100
slug: chart-xamarin-migration
---

# Migrating the Chart from Xamarin.Forms to .NET MAUI

The Telerik UI for .NET MAUI Chart preserves the same API as its Xamarin counterpart except for the configuration options listed in this article.

The table in the following sections list the differences between the APIs of the Xamarin.Forms Chart and .NET MAUI Chart.

## Namespaces Differences

When migrating the Chart from Xamarin to .NET MAUI, consider the following differences in the namespaces:

| Control | Control name | XAML Namespace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin Chart | `RadChart` | xmlns:telerikChart="clr-namespace:Telerik.XamarinForms.Chart;assembly=Telerik.XamarinForms.Chart" | using Telerik.XamarinForms.Chart; |
| .NET MAUI Chart | `RadChart` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls.Compatibility.Chart; |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
* [.NET MAUI Chart Product Page](https://www.telerik.com/maui-ui/chart)
* [.NET MAUI Chart Forum Page](https://www.telerik.com/forums/maui?tagId=1765)
