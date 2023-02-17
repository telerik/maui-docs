---
title: Migrate from Xamarin.Forms
page_title: .NET MAUI Entry Documentation - Migrate from Xamarin
description: "Learn how to migrate from Xamarin.Forms Entry to .NET MAUI Entry control."
position: 2
slug: entry-migrate-from-xamarin
---

# Migrate from Xamarin.Forms Entry to .NET MAUI Entry

Overall, Telerik .NET MAUI Entry control preserves the same API as Xamarin.Forms Entry with a few changes and improvements listed below.

## Migrate Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin Entry | `RadEntry` | xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input" | using Telerik.XamarinForms.Input; | 
| .NET MAUI Entry | `RadEntry` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## API Changes

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

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
