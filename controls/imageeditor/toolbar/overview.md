---
title: Overview
page_title: .NET MAUI ImageEditor Documentation - Toolbar
description: "Review all built-in toolbar items you can use in the Telerik UI for .NET MAUI ImageEditor."
position: 0
slug: imageeditor-toolbar
---

# .NET MAUI ImageEditor Toolbar

The **ImageEditorToolbar for .NET MAUI** includes items for editing the image in the ImageEditor, alternatively you could customize the shown editing options according to your needs.

## Built-in Toolbar items for image editing

The biult-in toolbar items are described in the tables below:

### Toolbar items available on mobile - Android and iOS

The table below shows the built-in toolbar items available for mobile -  Android and iOS:

| Toolbar Item | Description |
| ------------ | ------- |
| `ImageEditorTransformationsToolbarItem` | Allows you to choose one of the available transformaions options like crop, resize, rotate and flip |
| `ImageEditorFiltersToolbarItem` | Allows you to choose one of the available filteres like blur, sharpen, contrast and more |
| `ImageEditorUndoToolbarItem` | Undoes the last executed action on the image in the ImageEditor |
| `ImageEditorRedoToolbarItem` | Redoes the last executed action on the image in the ImageEditor |

### Toolbar items available on desktop - WinUI and MacCatalyst

The table below shows the built-in toolbar items available for desktop - WinUI and MacCatalyst:

| Toolbar Item | Description |
| ------------ | ------- |
| `ImageEditorCropOptionsToolbarItem` | Represents a button displaying a crop options panel |
| `ImageEditorResizeOptionsToolbarItem` | Represents a button displaying a resize options panel |
| `ImageEditorRotateLeftToolbarItem` | Rotates the image 90 degrees to the left |
| `ImageEditorRotateRightToolbarItem` | Rotates the image 90 degrees to the right |
| `ImageEditorFlipHorizontalToolbarItem` | Flips the image in horizontal direction |
| `ImageEditorFlipVerticalToolbarItem` | Flips the image in vertical direction |
| `ImageEditorFilterOptionsToolbarItem` | Represents a button displaying a filter options panel for applying filters like blur, hue, saturation, etc. |
| `ImageEditorUndoToolbarItem` | Undoes the last executed action on the image in the ImageEditor |
| `ImageEditorRedoToolbarItem` | Redoes the last executed action on the image in the ImageEditor |
| `SeparatorToolbarItem` | Represents a separator between the toolbar items |

## Toolbar Configuration

* Attach the `RadImageEditorToolbar` to the `RadImageEditor` control by setting the `ImageEditor`(of type `RadImageEditor`)property.

<snippet id='imageeditor-getting-started-xaml'/>

* By default the items in the `ImageEditorToolbar` are auto-populated. You could change this by setting the `RadImageEditorToolbar.AutoGenerateItems`(of type `bool`) to `False`. The default value is `True`.

### Common properties

`RadImageEditorToolbar` inherits from the `RadToolbar`({%slug toolbar-overview%}). All properties for configuration and styling available for the RadToolbar applies to the RadImageEditorToolbar

 >important For the ImageEditorToolbar example review the ImageEditor Getting Started example in the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).


## See Also

- [Saving Images]({%slug imageeditor-saving-image%})
- [Loading Images]({%slug imageeditor-loading-image%})
- [Zooming Images]({%slug imageeditor-zooming-image%})
