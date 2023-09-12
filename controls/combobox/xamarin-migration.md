---
title: Migrating from Xamarin
page_title: .NET MAUI ComboBox Documentation - Migrate from Xamarin
description: Learn how to migrate from Xamarin.Forms ComboBox to .NET MAUI ComboBox control.
position: 100
tags: dot net maui, .net maui vs xamarin, maui vs xamarin, net maui vs xamarin, migration, xamarin.forms
previous_url: /controls/combobox/migrate-from-xamarin
slug: combobox-migrate-from-xamarin
---

# Migrate from Xamarin.Forms ComboBox to .NET MAUI ComboBox

The Telerik UI for .NET MAUI ComboBox preserves the same API as its Xamarin counterpart except for the configuration options listed in this article.

The tables in the following sections list any differences between the APIs of the Xamarin.Forms ComboBox and .NET MAUI ComboBox.

## Migrate the Namespaces

| Control | Control name | C# Namespace| XAML Namespcace |
| --------------- | --------------- | --------------- | --------------------------------------------------- |
| Xamarin ComboBox | `RadComboBox` | xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input" | using Telerik.XamarinForms.Input; |
| .NET MAUI ComboBox | `RadComboBox` |  xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## API Changes

| Xamarin ComboBox | .NET MAUI ComboBox |
| ------------- | --------------- |
| N/A | `BorderBrush` |
| N/A | `SelectionBoxTemplate` |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
* [.NET MAUI ComboBox Product Page](https://www.telerik.com/maui-ui/checkbox)
* [.NET MAUI ComboBox Forum Page](https://www.telerik.com/forums/maui?tagId=1937)
