---
title: Styling
page_title: .NET MAUI ImageEditor Documentation - Toolbar Styling
description: "Review all styling oprions that can be applied to the ImageEditor toolbar for .NET MAUI."
position: 2
slug: imageeditor-toolbar-styling
---

# .NET MAUI ImageEditor Toolbar Styling

You can style the Toolbar using the Flexible Styling API.

## Style the toolbar

Style the Toolbar using the following properties:

* `BackgroundColor`(`Microsoft.Maui.Graphics.Color`)&mdash;Specifies the background color of the toolbar.
* `BorderColor`(`Microsoft.Maui.Graphics.Color`)&mdash;Specifies the color of the border around the toolbar.
* `BorderThickness`(`Microsoft.Maui.Thickness`)&mdash;Specifies the thickness of the border around the toolbar.
* `CornerRadius`(`Microsoft.Maui.Thickness`)&mdash;Specifies the corner radius of the border around the toolbar.
* `Style`(of type `Microsoft.Maui.Controls.Style`, with targe type `Telerik.Maui.Controls.ToolbarContentView`)&mdash;Specifies the style of the toolbar. 

## Style the toolbar elements

* `OverflowMenuButtonStyle`(`Microsoft.Maui.Controls.Style` with target type `Telerik.Maui.Controls.OverflowMenuButtonToolbarItemView`)&mdash;Specifies the Style applied to the overflow menu button in the toolbar. 
* `BackNavigationButtonStyle`(`Microsoft.Maui.Controls.Style` with target type `Telerik.Maui.Controls.BackNavigationButtonToolbarItemView`)&mdash;Specifies the Style applied to the back navigation button in the toolbar. 
* `ScrollForwardButtonStyle`(`Microsoft.Maui.Controls.Style` with target type `Telerik.Maui.Controls.ScrollForwardButtonToolbarItemView`)&mdash;Specifies the Style applied to the forward scroll button in the toolbar. 
* `ScrollBackwardButtonStyle`(`Microsoft.Maui.Controls.Style` with target type `Telerik.Maui.Controls.ScrollBackwardButtonToolbarItemView`)&mdash;Specifies the Style applied to the backward scroll button in the toolbar. 

## Style the Toolbar Items

Each toolbar item has a `Style` property and the target type of the oproperty is the corresponding `ToolbarItemView`:

| Toolbar Item | Style Target type |
| ------------ | ------- |
| `ImageEditorTransformationsToolbarItem` | `NavigationButtonToolbarItem` |
| `ImageEditorFiltersToolbarItem` | `ImageEditorFilterOptionsToolbarItemView` |
| `ImageEditorCropOptionsToolbarItem` | `ImageEditorCropOptionsToolbarItemView` |
| `ImageEditorResizeOptionsToolbarItem` | `ImageEditorResizeOptionsToolbarItemView` |
| `ImageEditorRotateLeftToolbarItem` | `ButtonToolbarItemView` |
| `ImageEditorRotateRightToolbarItem` | `ButtonToolbarItemView` |
| `ImageEditorFlipHorizontalToolbarItem` | `ButtonToolbarItemView` |
| `ImageEditorFlipVerticalToolbarItem` | `ButtonToolbarItemView` |
| `ImageEditorFilterOptionsToolbarItem` | Represents a button displaying a filter options panel for applying filters like blur, hue, saturation, etc. |
| `ImageEditorUndoToolbarItem` | `ButtonToolbarItemView` |
| `ImageEditorRedoToolbarItem` | `ButtonToolbarItemView` |
| `ImageEditorBrightnessToolbarItem` | `NavigationButtonToolbarItemView` |
| `ImageEditorHueToolbarItem` | `NavigationButtonToolbarItemView` |
| `ImageEditorSaturationToolbarItem` | `NavigationButtonToolbarItemView` |
| `ImageEditorBlurToolbarItem` | `NavigationButtonToolbarItemView` |
| `ImageEditorSharpenToolbarItem` | `NavigationButtonToolbarItemView` |
| `ImageEditorContrastToolbarItem` | `NavigationButtonToolbarItemView` |
| `SeparatorToolbarItem` | `SeparatorToolbarItemView` |
| `LabelToolbarItem` | `LabelToolbarItemView` |
| `ImageEditorCancelToolbarItem` | `ButtonToolbarItemView` |
| `ImageEditorApplyToolbarItem` | `ButtonToolbarItemView` |
| `ImageEditorOptionsToolbarItem` | `ImageEditorOptionsToolbarItemView` |

Style the content of the toolbar items 

| Toolbar options content styling |
| ------------ | ------- |
| Style the content of the Crop Options Toolbar Item | `ImageEditorCropOptionsToolbarItemViewContent` |
| Style the content of the Filter Options Toolbar Item | `ImageEditorFilterOptionsToolbarItemView` |
| Style the content of the Resize Options Toolbar Item | `ImageEditorResizeOptionsToolbarItemView` |
| Style the content of the Options Toolbar Item | `ImageEditorOptionsToolbarItemViewContent` |

##  Display text and or image in the toolbar item 

* `DisplayOptions`(enum of type `Telerik.Maui.Controls.ToolbarItemDisplayOptions`) property allows you to display text, image in the toolbar or in a combination of both. The options are `Text` and `Image`. This enum type supports a bitwise combination of its members to enable morethan one option.

 Position the image relative to the text in the toolbar item by setting the `ImagePosition`(enum of type `Telerik.Maui.Controls.ToolbarItemImagePosition`). The available options are: 
	* `Left`&mdash;The image is displayed to the left of the text.
	* `Top`&mdash;The image is displayed at the top of the text.
	* `Right`&mdash;The image is displayed to the right of the text.
	* `Bottom`&mdash;The image is displayed at the bottom of the text.
 
The default value is `Left`.

**Example for styling the Hue, Brightness and Button toolbar Items**

The XAML definition: 

<snippet id='imageeditor-toolbar-styling'/>

And the style in the page's repources: 

<snippet id='imageeditor-styling-button-toolbar-style'/>

>important For the ImageEditor Toolbar Styling example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## See Also

- [Saving Images]({%slug imageeditor-saving-image%})
- [Loading Images]({%slug imageeditor-loading-image%})
- [Zooming Images]({%slug imageeditor-zooming-image%})
