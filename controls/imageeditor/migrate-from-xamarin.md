---
title: Migrate from Xamarin.Forms
page_title: .NET MAUI ImageEditor Documentation - Migrate from Xamarin
description: "Learn how to migrate from Xamarin.Forms ImageEditor to .NET MAUI ImageEditor control."
position: 1
slug: imageeditor-migrate-from-xamarin
---

# Migrate from Xamarin.Forms ImageEditor to .NET MAUI ImageEditor

Overall, Telerik .NET MAUI ImageEditor control preserves the same API as Xamarin.Forms ImageEditor with a few changes and improvements listed in the tables below:

## Migrate Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin ImageEditor | `RadImageEditor` | `xmlns:telerikImageEditor="clr-namespace:Telerik.XamarinForms.ImageEditor;assembly=Telerik.XamarinForms.ImageEditor"` | `using Telerik.XamarinForms.ImageEditor;` | 
| .NET MAUI ImageEditor | `RadImageEditor` | `xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"` | `using Telerik.Maui.Controls;` |


## API Changes

| Xamarin ImageEditor | .NET MAUI ImageEditor |
| ------------- | --------------- |
| - | support for exporting images as `Gif` |
| - | support for exporting images as `Bmp` |
| - | `UndoCommand` |
| - | `RedoCommand` |
| - | `RotateBackwardCommand` |
| - | `SaturationInteractiveCommand` |
| - | `BrightnessInteractiveCommand` |
| - | `BlurInteractiveCommand` |
| - | `ContrastInteractiveCommand` |
| - | `HueInteractiveCommand` |
| - | `SharpenInteractiveCommand` |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
