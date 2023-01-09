---
title: Commands
page_title: .NET MAUI ImageEditor Documentation - Commands
description: "Review all commands .NET MAUI ImageEditor control provides like hue, rotate, crop, saturation, brightness and more."
position: 10
slug: imageeditor-commands
---

# .NET MAUI ImageEditor Commands

This article shows all the commands available in the ImageEditor for .NET MAUI. 

## All built-in and interactive commands

ImageEditor for .NET MAUI provides commands for programatically editing the image without the usage of the ImageEditorToolbar. The available commands are:

* `CropCommand`(`ICommand`)&mdash;Crop the image.
The `CropCommandContext` object is passed as a parameter to the `CropCommand`. The CropCommandContext has the following properties:
	* `Geometry`(of type `Telerik.XamarinForms.Common.RadGeometry`)&mdash;Specifies the geometry of the crop selection.
	* `Bounds`(of type `Rectangle`)&mdash;Used to get the current crop bounding rectangle.

* `CropInteractiveCommand`(`ICommand`)&mdash;Initiates the crop action.

* `ResizeCommand`&mdash;For image resizing. 
The `ResizeCommandContext` object is passed as a parameter to the `ResizeCommand`. The ResizeCommandContext has the following property:
	* `Size`(of type`Xamarin.Forms.Size`)&mdash;Specifies the size which will be used to resize the image.

* `RotateLeftCommand`(`ICommand`): for image rotation 90 degree to the left.

* `RotateRightCommand`: for image rotation 90 degree to the right.

* `BlurCommand`&mdash;Applies blur to the image.
The `BlurCommandContext` object is passed as a parameter to the `BlurCommand`. The BlurCommandContext has the following property:
	* `Blur`(`int`)&mdash;Specifies the blur value.

* `BlurInteractiveCommand`(`ICommand`)&mdash;Initiates the blur action.

* `BrightnessCommand`(`ICommand`)&mdash;Changes the brightness of the image.
The `BrightnessCommandContext` object is passed as a parameter to the `BrightnessCommand`. The BrightnessCommandContext has the following property:
	* `Brightness`(`double`)&mdash;Specifies the brightness value.

* `BrightnessInteractiveCommand`(`ICommand`)&mdash;Initiates the brightness action.

* `ContrastCommand`(`ICommand`)&mdash;Changes the image contrast.
The `ContrastCommandContext` object is passed as a parameter to the `ContrastCommand`. The ContrastCommandContext has the following property:
	* `Contrast`(`double`)&mdash;Specifies the contrast value.


* `ContrastInteractiveCommand`(`ICommand`)&mdash;Initiates the contrast action.

* `HueCommand`(`ICommand`)&mdash;Changes the image hue.
The `HueCommandContext` object is passed as a parameter to the `HueCommand`. The HueCommandContext has the following property:
	* `Hue`(`double`)&mdash;Specifies the hue value.

* `HueInteractiveCommand`(`ICommand`)&mdash;Initiates the hue action.

* `SaturationCommand`(`ICommand`):&mdash;Changes the image saturation.
The `SaturationCommandContext` object is passed as a parameter to the `SaturationCommand`. The SaturationCommandContext has the following property:
	* `Saturation`(`double`)&mdash;Specifies the saturation value.

* `SaturationInteractiveCommand`(`ICommand`)&mdash;Initiates the saturation action.

* `SharpenCommand`(`ICommand`)&mdash;Changes the image sharpness.
The `SaturationCommandContext` object is passed as a parameter to the `SharpenCommand`. The SharpenCommandContext has the following property:
	* `Sharpen`(`int`)&mdash;Specifies the sharpen value.

* `SharpenInteractiveCommand`(`ICommand`)&mdash;Initiates the sharpen action.

* `FlipHorizontalCommand`(`ICommand`)&mdash;Flips the image horizontally.

* `FlipVerticalCommand`(`ICommand`)&mdash;Flips the image vertically.

Commands which cancel/apply the changes made in interactive commands:

* `CancelInteractiveCommand`&mdash;Cancels the changes done in interactive command such as `Telerik.XamarinForms.ImageEditor.RadImageEditor.CropInteractiveCommand`.

* `ApplyInteractiveCommand`&mdash;Applies the changes done in interactive command such as `Telerik.XamarinForms.ImageEditor.RadImageEditor.CropInteractiveCommand`.

>important When using the **Interactive Commands** you can apply the changes using `ApplyInteractiveCommand` and cancel the changes using `CancelInteractiveCommand`.

* `UndoCommand`(`ICommand`)&mdash;Gets the command for the undo action.

* `RedoCommand`(`ICommand`)&mdash;Gets the command for the redo action.

* `RotateBackwardCommand`(`ICommand`)&mdash;Rotates the image backwards.

## Commands iherited from the Toolbar control

* `NavigateCommand`(`ICommand`)&mdash;Gets a command for navigating to the next level of the toolbar hierarchy. The command accepts a collection of `Telerik.Maui.Controls.ToolbarItems` as a parameter.
* `NavigateBackCommand`(`ICommand`)&mdash;Gets a command for navigating back to the previous level of the toolbar hierarchy. The previous `Telerik.Maui.Controls.ToolbarItems` stored in the navigation stack from the last invocation of the `Telerik.Maui.Controls.RadToolbar.NavigateCommand` are restored in the toolbar.
* `ScrollForwardCommand`(`ICommand`)&mdash;Gets a command for scrolling the contents of the toolbar in forward direction. This command is applicable when the `RadToolbar.OverflowMode` is set to `Scroll`.
* `ScrollBackwardCommand`(`ICommand`)&mdash;Gets a command for scrolling the contents of the toolbar in backward direction. This command is applicable when the `RadToolbar.OverflowMode` is set to Scroll.


### Example


## See Also

- [Custom Toolbar]({%slug imageeditor-custom-toolbar%})
- [Toolbar Styling]({%slug imageeditor-toolbar-styling%})