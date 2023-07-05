---
title: Migrating from Xamarin
page_title: Migrating the CheckBox from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin CheckBox to the Telerik UI for .NET MAUI framework by updating the namespaces and the incompatible NuGet packages.
position: 20
slug: checkbox-migrate-from-xamarin
---

# Migrating the CheckBox from Xamarin to .NET MAUI

Telerik .NET MAUI CheckBox control preserves the same API as Xamarin.Forms CheckBox with a few changes and improvements listed in the tables below:

## Migrating the Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin CheckBox | `RadCheckBox` | xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.XamarinForms.Primitives" | using Telerik.XamarinForms.Primitives; |
| .NET MAUI CheckBox | `RadCheckBox` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## Modifying the API

| Xamarin CheckBox | .NET MAUI CheckBox |
| ------------- | --------------- |
| - | `CornerRadius` |
| `CheckBoxUserCommand` | - |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
- [.NET MAUI CheckBox Product Page](https://www.telerik.com/maui-ui/checkbox)
- [.NET MAUI Forum Page](https://www.telerik.com/forums/maui?tagId=1853)
