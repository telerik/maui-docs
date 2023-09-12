---
title: Migrating from Xamarin
page_title: Migrating the Button from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin Button to the Telerik UI for .NET MAUI Button by updating the namespaces, the incompatible NuGet packages and API.
tags: dot net maui, .net maui vs xamarin, maui vs xamarin, net maui vs xamarin, migration, xamarin.forms
position: 100
slug: button-xamarin-migration
---

# Migrating the Button from Xamarin.Forms to .NET MAUI

Telerik .NET MAUI Button control inherits from .NET MAUI Button. The Telerik Xamarin.Forms Button inherits from Xamarin.Form Button.

The tables in the following sections list the differences between the APIs of the Xamarin.Forms Button and .NET MAUI Button.

## Namespaces Differences

When migrating the Button from Xamarin to .NET MAUI, consider the following differences in the namespaces:

| Control | Control name | XAML Namespace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin Button | `RadButton` | xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input" | using Telerik.XamarinForms.Input; |
| .NET MAUI Button | `RadButton` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
* [.NET MAUI Button Product Page](https://www.telerik.com/maui-ui/button)
* [.NET MAUI Button Forum Page](https://www.telerik.com/forums/maui?tagId=1764)
