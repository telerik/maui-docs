---
title: Migrating from Xamarin
page_title: Migrating the ImageEditor from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin ImageEditor to the Telerik UI for .NET MAUI framework by updating the namespaces and the incompatible NuGet packages.
position: 20
slug: imageeditor-migrate-from-xamarin
---

# Migrating the ImageEditor from Xamarin to .NET MAUI

Telerik .NET MAUI ImageEditor control preserves the same API as Xamarin.Forms ImageEditor with a few changes and improvements listed in the tables below:

## Migrating the Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin ImageEditor | `RadImageEditor` | xmlns:telerikImageEditor="clr-namespace:Telerik.XamarinForms.ImageEditor;assembly=Telerik.XamarinForms.ImageEditor" | using Telerik.XamarinForms.ImageEditor; |
| .NET MAUI ImageEditor | `RadImageEditor` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |


## Modifying the API

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

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
- [.NET MAUI ImageEditor Product Page](https://www.telerik.com/maui-ui/imageeditor)
- [.NET MAUI Forum Page](https://www.telerik.com/forums/maui?tagId=1853)
