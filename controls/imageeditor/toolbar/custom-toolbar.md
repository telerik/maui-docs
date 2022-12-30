---
title: Custom Toolbar
page_title: .NET MAUI ImageEditor Documentation - Custom Toolbar
description: "Review all built-in toolbar items you can use in the Telerik UI for .NET MAUI ImageEditor."
position: 1
slug: imageeditor-custom-toolbar
---

# .NET MAUI ImageEditor Custom Toolbar

The ImageEditor Toolbar can be fully customized. You can populate the toolbar with the ToolbarItems needed for editing the image. 

Each toolbar item executes the appropriate cmmand related to it. 

## Toolbar items

When you customize the toolbar you could include the following editing capabilities:

### Applying image transformations

* The toolbar items for applying **image transformations** to the image are:
	* `ImageEditorCropToolbarItem`
	* `ImageEditorResizeToolbarItem`
	* `ImageEditorRotateLeftToolbarItem`
	* `ImageEditorRotateRightToolbarItem`
	* `ImageEditorFlipHorizontalToolbarItem`
	* `ImageEditorFlipVerticalToolbarItem`

>tip To group the transformations you could use the `ImageEditorTransformationsToolbarItem`.

### Applying filters

* The toolbar items for applying **filters** to the image are:
	* `ImageEditorHueToolbarItem`
	* `ImageEditorSaturationToolbarItem`
	* `ImageEditorBrightnessToolbarItem`
	* `ImageEditorContrastToolbarItem`
	* `ImageEditorBlurToolbarItem`
	* `ImageEditorSharpenToolbarItem`

>tip To group the filters you could use the `ImageEditorFiltersToolbarItem` on mobile and `ImageEditorFilterOptionsToolbarItem` on desktop.

## Reversing and re-applying actions

* The toolbar items for reversing and re-applying actions are:
	* `ImageEditorUndoToolbarItem`
	* `ImageEditorRedoToolbarItem`
	* `ImageEditorResetToolbarItem`

## Navigation toolbar item

For navigating in the toolbar use the `NavigationButtonToolbarItem`.

## Zooming toolbar item

To fit the image in the available screen space use the `ImageEditorZoomToFitToolbarItem`. 

## Custom toolbar item

* For applying custom command in the ImageEditorToolbar use the  use the `ButtonToolbarItem`. The coomand allows you to execute an arbitrary user-defined command from the toolbar. It exposes the following properties:
	* `Command`(`ICommand`)&mdash;Specifies the command to execute.
	* `CommandParameter`(`object`)&mdash;Specifies a parameter to be passed to the command upon execution.
	* `Clicked` event&mdash;Raised when the button is clicked.

## Separate the toolbar items

You can easily separate the toolbar items using the `SeparatorToolbarItem`.

>important For the ImageEditor CustomToolbar example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## See Also

- [Saving Images]({%slug imageeditor-saving-image%})
- [Loading Images]({%slug imageeditor-loading-image%})
- [Zooming Images]({%slug imageeditor-zooming-image%})
