---
title: RadioButton
page_title: .NET MAUI Toolbar Documentation - RadioButton ToolbarItem
description: Review the Toolbar radio button item for .NET MAUI.
position: 3
slug: toolbar-items-radio-button
---

# .NET MAUI RadioButton ToolbarItem

You can add radio buttons in the toolbar control using the `RadioButtonToolbarItem`.

The available properties for configuration are:

* `IsSelected`(`bool`)&mdash;Specifies whether the button is selected.
* `Text`(`string`)&mdash;Defines the text(target type `Label`) in the toolbar item. You can display an image next to the text.
* `ImageSource`(`Microsoft.Maui.Controls.ImageSource`)&mdash;Specifies the source of the image to display in the toolbar item.
* `GroupName`(`string`)&mdash;Specifies the unique name of the radio group. The radio group allows single selection for all radio toolbar items with the same radio group name. 

## Events

* `IsSelectedChanged`&mdash:Raised when the `IsSelected` property has changed.
* `Clicked`&mdash;Raised when the button is clicked.

## Commands

The available commands are:

* `Command`(`ICommand`)&mdash;Specfies the command to execute when the button is clicked.
* `Command`(`object`)&mdash;Specfies the parameter of the command, which is executed when the button is clicked.

## Styling

Use the `Style` property with target type `Telerik.Maui.Controls.RadioButtonToolbarItemView`. The properties that can be applied through style are: `IsSelected` and all properties available for the [ButtonToolbarItemView]({%slug toolbar-items-button%}#styling), [LabelToolbarItemView]({%slug toolbar-items-label%}#styling) and [ToolbarItemView]({%slug toolbar-items%}#styling).

## See Also

- [SplitButton ToolbarItem]({%slug toolbar-items-split-button%})
- [ToggleButton ToolbarItem]({%slug toolbar-items-toggle-button%})
- [Label ToolbarItem]({%slug toolbar-items-label%})
- [NavigationButton ToolbarItem]({%slug toolbar-items-navigation-button%})
- [ListPicker ToolbarItem]({%slug toolbar-items-listpicker-button%})
- [Group ToolbarItem]({%slug toolbar-items-group%})
- [Slider ToolbarItem]({%slug toolbar-items-slider%})
