---
title: Overview
page_title: .NET MAUI ImageEditor Documentation - Toolbar
description: "Review all built-in toolbar items you can use in the Telerik UI for .NET MAUI ImageEditor."
position: 0
slug: imageeditor-toolbar
---

# .NET MAUI ImageEditor Toolbar

The **ImageEditorToolbar for .NET MAUI** includes items for editing the image in the ImageEditor, alternatively you could customize the shown editing options according to your needs.

## Configuration of the ImageEditorToolbar

`RadImageEditorToolbar` inherits from the [RadToolbar]({%slug toolbar-overview%}). All properties for configuration and styling available for the RadToolbar apply to the RadImageEditorToolbar.

The configuration properties are described below

* Attach the `RadImageEditorToolbar` to the `RadImageEditor` control by setting the `ImageEditor`(of type `RadImageEditor`)property.

<snippet id='imageeditor-getting-started-xaml'/>

* By default the items in the `ImageEditorToolbar` are auto-populated. You could change this by setting the `RadImageEditorToolbar.AutoGenerateItems`(of type `bool`) to `False`. The default value is `True`.

* By setting the `Orientation`(enum of type`Telerik.Maui.Controls.ToolbarOrientation`) property you can specify the orientation of the toolbar. The available options are `Horizontal` and `Vertical`. The default value is `Horizontal.`
* `OptionsPanel`(`Telerik.Maui.Controls.RadToolbarOptionsPanel`)&mdash;Specifies the options panel associated with this toolbar.
* `ItemSpacing`(`double`)&mdash;Specifies the spacing in pixels between the items in the toolbar. The default value is `8`.
* `LineSpacing`(`double`)&mdash;Specifies the spacing in pixels between the lines of items in the toolbar. This property has effect when the toolbar is in a multi-line wrap overflow mode. The default value is `8`.

### Configuration of the Overflow menu

* `OverflowMode`(enum of type `Telerik.Maui.Controls.ToolbarOverflowMode`)&mdash; Specifies the overflow mode when the items in the toolbar cannot fit in the available space. The available options are:
	* `DropDown`(the default mode)&mdash;When the toolbar items cannot fit in the available space, they are placed in the overflow drop-down menu.
	* `Scroll`&mdash;When the toolbar items cannot fit in the available space, they are scrolled horizontally or vertically, based on the orienatation of the toolbar.
	* `Wrap`&mdash;When the toolbar items cannot fit in the available space, they are wrapped horizontally or vertically on multiple lines, based on the orientation of the toolbar.

* `OverflowMenuButtonVisibility`(enum of type `Telerik.Maui.Controls.ToolbarButtonVisibilityMode`)&mdash;Specifies the visibility mode of the overflow menu button in the toolbar. The available options are:
	* `Auto`(the default mode)&mdash;The button visibility is determined automatically, based on the associated command.
	* `Visible`(the default mode)&mdash;The button is always visible in the toolbar, regardless of the associated command.
	* `Hidden`(the default mode)&mdash;The button is always hidden from the toolbar, regardless of the associated command.

* `OverflowMenuButtonTemplate`(`ControlTemplate`)&mdash;Defines the ControlTemplate applied to the overflow menu button in the toolbar.
* `OverflowMenuButtonStyle`(`Style` with target type `Telerik.Maui.Controls.OverflowMenuButtonToolbarItemView`)&mdash;Specifies the style applied to the Overflow menu button.

### Configuration of the back navigation button

* `BackNavigationButtonVisibility`(enum of type `Telerik.Maui.Controls.ToolbarButtonVisibilityMode`)&mdash;Specifies the visibility mode of the back navigation button in the toolbar. The available options are:
	* `Auto`(the default mode)&mdash;The button visibility is determined automatically, based on the associated command.
	* `Visible`(the default mode)&mdash;The button is always visible in the toolbar, regardless of the associated command.
	* `Hidden`(the default mode)&mdash;The button is always hidden from the toolbar, regardless of the associated command.

* `BackNavigationButtonTemplate`(`ControlTemplate`)&mdash;Defines the ControlTemplate applied to the back navigation button in the toolbar.
* `BackNavigationButtonStyle`(`Style` with target type `Telerik.Maui.Controls.BackNavigationButtonToolbarItemView`)&mdash;Specifies the style applied to the back navigation button.

### Configuration for the scroll button, scroll forward and backward buttons

* `ScrollButtonsVisibility`(enum of type `Telerik.Maui.Controls.ToolbarButtonVisibilityMode`)&mdash;Specifies the visibility mode of the scroll buttons in the toolbar. The available options are:
	* `Auto`(the default mode)&mdash;The button visibility is determined automatically, based on the associated command.
	* `Visible`(the default mode)&mdash;The button is always visible in the toolbar, regardless of the associated command.
	* `Hidden`(the default mode)&mdash;The button is always hidden from the toolbar, regardless of the associated command.

* `ScrollForwardButtonTemplate`(`ControlTemplate`)&mdash;Defines the ControlTemplate applied to the forward scroll button in the toolbar.
* `ScrollForwardButtonStyle`(`Style` with target type `Telerik.Maui.Controls.ScrollForwardButtonToolbarItemView`)&mdash;Defines the style applied to the forward scroll button in the toolbar.
* `ScrollBackwardButtonTemplate`(`ControlTemplate`)&mdash;Defines the ControlTemplate applied to the backward dscroll button in the toolbar.
* `ScrollBackwardButtonStyle`(`Style` with target type `Telerik.Maui.Controls.ScrollBackwardButtonToolbarItemView`)&mdash;Defines the style applied to the backward scroll button in the toolbar.


## See Also

- [Saving Images]({%slug imageeditor-saving-image%})
- [Loading Images]({%slug imageeditor-loading-image%})
- [Zooming Images]({%slug imageeditor-zooming-image%})
