---
title: Migrate from Xamarin.Forms
page_title: .NET MAUI CheckBox Documentation - Migrate from Xamarin
description: "Learn how to migrate from Xamarin.Forms CheckBox to .NET MAUI CheckBox control."
position: 1
slug: checkbox-migrate-from-xamarin
---

# Migrate from Xamarin.Forms CheckBox to .NET MAUI CheckBox

Overall, Telerik .NET MAUI CheckBox control preserves the same API as Xamarin.Forms CheckBox with a few changes and improvements listed in the tables below:

## Migrate the Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin CheckBox | `RadCheckBox` | xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.XamarinForms.Primitives" | using Telerik.XamarinForms.Primitives; | 
| .NET MAUI CheckBox | `RadCheckBox` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## API Changes

| Xamarin CheckBox | .NET MAUI CheckBox |
| ------------- | --------------- |
| - | `CornerRadius` |
| `CheckBoxUserCommand` | - |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})

