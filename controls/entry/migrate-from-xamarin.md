---
title: Migrating from Xamarin
page_title: Migrating the Entry from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin Entry to the Telerik UI for .NET MAUI framework by updating the namespaces and the incompatible NuGet packages.
position: 20
slug: entry-migrate-from-xamarin
---

# Migrating the Entry from Xamarin to .NET MAUI

Telerik .NET MAUI Entry control preserves the same API as the Xamarin.Forms Entry with a few changes and improvements listed below.

## Migrating the Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin Entry | `RadEntry` | xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input" | using Telerik.XamarinForms.Input; |
| .NET MAUI Entry | `RadEntry` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## Modifying the API

| Xamarin Entry | .NET MAUI Entry |
| ------------- | --------------- |
| `WatermarkText` | `Placeholder` |
| `WatermarkTextColor` | `PlaceholderColor` |
| - | `CharacterSpacing` |
| - | `IsTextPredictionEnabled` |
| - | `ReturnType` |
| - | `ClearButtonVisibility` |
| `CompletedCommand` | `ReturnCommand` |
| `BorderStyle.BorderColor` | `BorderBrush` |
| `BorderStyle.BorderThickness` | `BorderThickness` |
| `BorderStyle.CornerRadius` | `CornerRadius` |
| - | `ClearButtonColor` |
| - | `FocusedBorderBrush` |
| - | `FocusedBorderThickness` |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
- [.NET MAUI Entry Product Page](https://www.telerik.com/maui-ui/entry)
- [.NET MAUI Forum Page](https://www.telerik.com/forums/maui?tagId=1853)
