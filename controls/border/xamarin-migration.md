---
title: Migrating from Xamarin
page_title: Migrating the Border from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin Border to the Telerik UI for .NET MAUI Border by updating the namespaces, the incompatible NuGet packages and API.
tags: dot net maui, .net maui vs xamarin, maui vs xamarin, net maui vs xamarin, migration, xamarin.forms
position: 100
slug: border-xamarin-migration
---

# Migrating the Border from Xamarin.Forms to .NET MAUI

Telerik .NET MAUI Border control preserves the same API as Xamarin.Forms Border with a few changes and improvements.

The tables in the following sections list the differences between the APIs of the Xamarin.Forms Border and .NET MAUI Border.

## Namespaces Differences

When migrating the Border from Xamarin to .NET MAUI, consider the following differences in the namespaces:

| Control | Control name | XAML Namespace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin Border | `RadBorder` | xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.XamarinForms.Primitives" | using Telerik.XamarinForms.Primitives; |
| .NET MAUI Border | `RadBorder` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug sampleapps-overview %})
* [.NET MAUI Barcode Product Page](https://www.telerik.com/maui-ui/barcode)
* [.NET MAUI Barcode Forum Page](https://www.telerik.com/forums/maui?tagId=1780)
