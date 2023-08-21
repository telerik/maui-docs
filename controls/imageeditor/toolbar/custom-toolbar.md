---
title: Custom Toolbar
page_title: .NET MAUI ImageEditor Documentation - Custom Toolbar
description: Review all built-in toolbar items you can use in the Telerik UI for .NET MAUI ImageEditor.
position: 2
slug: imageeditor-custom-toolbar
---

# .NET MAUI ImageEditor Custom Toolbar

The ImageEditor Toolbar can be customized. You can populate the toolbar with the `ToolbarItems` needed for editing the image. 

Each toolbar item executes the proper command related to it. 

## Toolbar Items

When you customize the toolbar you can include the following editing capabilities:

### Applying Image Transformations

The toolbar items for applying **image transformations** to the image are:

* `ImageEditorCropToolbarItem`
* `ImageEditorResizeToolbarItem`
* `ImageEditorRotateLeftToolbarItem`
* `ImageEditorRotateRightToolbarItem`
* `ImageEditorFlipHorizontalToolbarItem`
* `ImageEditorFlipVerticalToolbarItem`

>tip To group the transformations you can use the `ImageEditorTransformationsToolbarItem`.

### Applying Filters

The toolbar items for applying **filters** to the image are:

* `ImageEditorHueToolbarItem`
* `ImageEditorSaturationToolbarItem`
* `ImageEditorBrightnessToolbarItem`
* `ImageEditorContrastToolbarItem`
* `ImageEditorBlurToolbarItem`
* `ImageEditorSharpenToolbarItem`

>tip To group the filters you can use the `ImageEditorFiltersToolbarItem` on mobile and `ImageEditorFilterOptionsToolbarItem` on desktop.

## Reversing and Re-applying Actions

The toolbar items for reversing and re-applying actions are:

* `ImageEditorUndoToolbarItem`
* `ImageEditorRedoToolbarItem`
* `ImageEditorResetToolbarItem`

## Navigation Toolbar Item

For navigating in the toolbar use the `NavigationButtonToolbarItem`.

## Zooming Toolbar Item

To fit the image in the available screen space use the `ImageEditorZoomToFitToolbarItem`. 

## Custom Toolbar Item

* `LabelToolbarItem`&mdash;Represents a label in the toolbar.

	* `Text`(`string`)&mdash;Specifies the text in the toolbar.
	* `ImageSource`(`Microsoft.Maui.Controls.ImageSource`)&mdash;Specifies the image in the toolbar.

* `ButtonToolbarItem`. The toolbar item allows you to execute an arbitrary user-defined command from the toolbar. It exposes the following properties:

	* `Command`(`ICommand`)&mdash;Specifies the command to execute.
	* `CommandParameter`(`object`)&mdash;Specifies a parameter to be passed to the command upon execution.
	* `Clicked` event&mdash;Raised when the button is clicked.

## Separate the Toolbar Items

You can separate the toolbar items using the `SeparatorToolbarItem`.

## Apply and Cancel Items

* `ImageEditorApplyToolbarItem`&mdash;Specifies a parameter to be passed to the command upon execution.
* `ImageEditorCancelToolbarItem`&mdash;Raised when the button is clicked.

## Example with Custom Toolbar

XAML definition of the `RadImageEditor` and `RadImageEditorToolbar`:

<snippet id='imageeditor-custom-toolbar'/>

and the image is loaded from Stream:

<snippet id='load-image-from-stream'/>

>important For the ImageEditor Custom Toolbar example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## Example with Custom Crop Toolbar

You can create a custom crop toolbar. Here is the XAML definition of the toolbar:

<snippet id='imageeditor-custom-crop-toolbar'/>

Here is the style applied to the `ButtonToolbarItem`:

<snippet id='imageeditor-buttontoolbar-style'/>

>important For the ImageEditor Custom Crop Toolbar example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## See Also

- [Saving Images]({%slug imageeditor-saving-image%})
- [Loading Images]({%slug imageeditor-loading-image%})
- [Zooming Images]({%slug imageeditor-zooming-image%})
