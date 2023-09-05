---
title: DropDownButton
page_title: .NET MAUI Toolbar Documentation - DropDownButon ToolbarItem
description: Review the Toolbar drop-down button item for .NET MAUI.
position: 3
slug: toolbar-items-dropdown-button
---

# .NET MAUI DropDownButton ToolbarItem

Add a button displaying a drop-down panel in the Toolbar control using the `DropDownButtonToolbarItem`.

The exposed properties are:

* `IsOpen`(`bool`)&mdash;Indicating whether the drop-down is currently open.
* `DropDownContentTemplate`(`ControlTemplate`)&mdash;Specifies the `ControlTemplate` of the drop-down content. The target type of this template is `Telerik.Maui.Controls.DropDownButtonToolbarItemViewContent.`
* `DropDownIndicatorTemplate`(`ControlTemplate`)&mdash;Specifies the `ControlTemplate` of the drop-down indicator. The target type of this template is `Telerik.Maui.Controls.DropDownButtonToolbarItemViewIndicator.`
* `Text`(`string`)&mdash;Defines the text(target type `Label`) in the toolbar item. You can display an image next to the text.
* `ImageSource`(`Microsoft.Maui.Controls.ImageSource`)&mdash;Specifies the source of the image to display in the toolbar item.

## Events

The exposed events are:

* `IsOpenChanged`&mdash;Raised when the `IsOpen` property has changed.
* `Clicked`&mdash;Raised when the button is clicked.

## Commands 

The available commands are:

* `Command`(`ICommand`)&mdash;Specifies the command to execute when the button is clicked.
* `CommandParameter`(`object`)&mdash;Specifies the parameter of the command, which is executed when the button is clicked.

## Styling

* `Style` property with target type `DropDownButtonToolbarItemView`. The properties exposed in the `DropDownButtonToolbarItemView` are:

* `IsOpen`(`bool`)&mdash;Indicating whether the drop-down is currently open.
* `DropDownHorizontalOffset`(`double`)&mdash;Specifies the horizontal offset in pixels of the drop-down from the button.
* `DropDownVerticalOffset`(`double`)&mdash;Specifies the vertical offset in pixels of the drop-down from the button.
* `DropDownIndicatorSpacing`(`double`)&mdash;Specifies the spacing in pixels between the drop-down indicator and the button content.
* `IsDropDownIndicatorVisible`(`bool`)&mdash;Indicating whether the drop-down indicator is visible in the button.
* `DropDownPlacement`(enum of type `Telerik.Maui.Controls.PlacementMode`)&mdash;
* `DropDownContentStyle`(`Style` with target type `Telerik.Maui.Controls.DropDownButtonToolbarItemViewContent`)&mdash;Specifies the style for the content in the drop-down.
* `DropDownIndicatorStyle`(`Style` with target type `Telerik.Maui.Controls.DropDownButtonToolbarItemViewIndicator`)&mdash;Specifies the style for the drop-down indicator.

All other properties that can be applied through style are the properties applicable for [ButtonToolbarItemView]({%slug toolbar-items-button%}#styling), [LabelToolbarItemView]({%slug toolbar-items-label%}#styling) and [ToolbarItemView]({%slug toolbar-items%}#styling).

## See Also

- [SplitButton ToolbarItem]({%slug toolbar-items-split-button%})
- [Label ToolbarItem]({%slug toolbar-items-label%})
- [Navigation Button ToolbarItem]({%slug toolbar-items-navigation-button%})
- [ListPicker ToolbarItem]({%slug toolbar-items-listpicker-button%})
- [Group ToolbarItem]({%slug toolbar-items-group%})
- [RadioButton ToolbarItem]({%slug toolbar-items-radio-button%})
- [Slider ToolbarItem]({%slug toolbar-items-slider%})
