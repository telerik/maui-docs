---
title: ToggleButton
page_title: .NET MAUI Toolbar Documentation - ToggleButton ToolbarItem
description: "Review the Toolbar toggle button item for .NET MAUI"
position: 0
slug: toolbar-items-toggle-button
---

# .NET MAUI ToggleButton ToolbarItem

Add a toggle button in the Toolbar control using the `ToggleButtonToolbarItem`.

The exposed properties are:

* `IsSelected`(`bool`)&mdash;Indicating whether the button is selected.

## Events

The exposed events are:

* `IsSelectedChanged`&mdash;Raised when the `IsSelected` property has changed.
* `Clicked`&mdash:Raised when the button is clicked.
The available commands are:

## Commands 

The available commands are:

* `Command`(`ICommand`)&mdash;Specfies the command to execute when the button is clicked.
* `CommandParameter`(`object`)&mdash;Specfies the parameter of the command, which is executed when the button is clicked.

## Styling

ToggleButtonToolbarItem has a `Style` property with target type `ToggleButtonToolbarItemView`. The property exposed in the `ToggleButtonToolbarItemView` is the `IsSelected` property.

All other properties that can be applied through style are the properties applicable for [ButtonToolbarItemView]({%slug toolbar-items-button%}#styling), [ToolbarItemView]({%slug toolbar-items%}#styling) and [LabelToolbarItemView]({%slug toolbar-items-label%}#styling)

## See Also

- [SplitButton ToolbarItem]({%slug toolbar-items-split-button%})
- [Label ToolbarItem]({%slug toolbar-items-label%})
- [NavigationButton ToolbarItem]({%slug toolbar-items-navigation-button%})
- [ListPicker ToolbarItem]({%slug toolbar-items-listpicker-button%})
- [Group ToolbarItem]({%slug toolbar-items-group%})
- [RadioButton ToolbarItem]({%slug toolbar-items-radio-button%})
- [Slider ToolbarItem]({%slug toolbar-items-slider%})
