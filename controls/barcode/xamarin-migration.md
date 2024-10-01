---
title: Migrating from Xamarin
page_title: Migrating the Barcode from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin Barcode to the Telerik UI for .NET MAUI Barcode by updating the namespaces, the incompatible NuGet packages and API.
tags: dot net maui, .net maui vs xamarin, maui vs xamarin, net maui vs xamarin, migration, xamarin.forms
position: 100
slug: barcode-xamarin-migration
---

# Migrating the Barcode from Xamarin.Forms to .NET MAUI

Telerik .NET MAUI Barcode control preserves the same API as its Xamarin counterpart except for the configuration options listed in this article.

The tables in the following sections list the differences between the APIs of the Xamarin.Forms Barcode and .NET MAUI Barcode.

## Namespaces Differences

When migrating the Barcode from Xamarin to .NET MAUI, consider the following differences in the namespaces:

| Control | Control name | XAML Namespace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin Barcode | `RadBarcode` | xmlns:telerikBarcode="clr-namespace:Telerik.XamarinForms.Barcode;assembly=Telerik.XamarinForms.Barcode" | using Telerik.XamarinForms.Barcode; |
| .NET MAUI Barcode | `RadBarcode` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls.Compatibility.Barcode; |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug sampleapps-overview %})
* [.NET MAUI Barcode Product Page](https://www.telerik.com/maui-ui/barcode)
* [.NET MAUI Barcode Forum Page](https://www.telerik.com/forums/maui?tagId=1780)
