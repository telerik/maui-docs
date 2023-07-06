---
title: Migrating from Xamarin
page_title: .NET MAUI ComboBox Documentation - Migrate from Xamarin
description: Learn how to migrate from Xamarin.Forms ComboBox to .NET MAUI ComboBox control.
position: 20
slug: combobox-migrate-from-xamarin
---

# Migrate from Xamarin.Forms ComboBox to .NET MAUI ComboBox

Compared API changes in Xamarin.Forms ComboBox and .NET MAUI ComboBox are described in the tables below:

## Migrate the Namespaces

| Control | Control name | C# Namespace| XAML Namespcace |
| --------------- | --------------- | --------------- | --------------------------------------------------- |
| Xamarin ComboBox | `RadComboBox` | xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input" | using Telerik.XamarinForms.Input; |
| .NET MAUI ComboBox | `RadComboBox` |  xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## API Changes

| Xamarin ComboBox | .NET MAUI ComboBox |
| ------------- | --------------- |
| - | `BorderBrush` |
| - | `SelectionBoxTemplate` |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
