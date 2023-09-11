---
title: Migrating from Xamarin
page_title: Migrating the CheckBox from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin CheckBox to the Telerik UI for .NET MAUI framework by updating the namespaces and the incompatible NuGet packages.
position: 100
tags: dot net maui, .net maui vs xamarin, maui vs xamarin, net maui vs xamarin, migration, xamarin.forms
previous_url: /controls/checkbox/migrate-from-xamarin
slug: checkbox-migrate-from-xamarin
---

# Migrating the CheckBox from Xamarin to .NET MAUI

The Telerik UI for .NET MAUI CheckBox preserves the same API as its Xamarin counterpart except for the configuration options listed in this article.

The tables in the following sections list any differences between the APIs of the Xamarin.Forms CheckBox and .NET MAUI CheckBox.

## Migrating the Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin CheckBox | `RadCheckBox` | xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.XamarinForms.Primitives" | using Telerik.XamarinForms.Primitives; |
| .NET MAUI CheckBox | `RadCheckBox` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## Modifying the API

| Xamarin CheckBox | .NET MAUI CheckBox |
| ------------- | --------------- |
| N/A | `CornerRadius` |
| `CheckBoxUserCommand` | N/A |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
- [.NET MAUI CheckBox Product Page](https://www.telerik.com/maui-ui/checkbox)
- [.NET MAUI Forum Page](https://www.telerik.com/forums/maui?tagId=1853)
