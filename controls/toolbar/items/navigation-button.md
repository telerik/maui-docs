---
title: NavigationButton
page_title: .NET MAUI Toolbar Documentation - NavigationButton ToolbarItem
description: Review the Toolbar navigation button item for .NET MAUI.
position: 3
slug: toolbar-items-navigation-button
---

# .NET MAUI NavigationButton ToolbarItem

Add a navigation button in the Toolbar control using the `NavigationButtonToolbarItem`. The `NavigationButtonToolbarItem` inherits from [ButtonToolbarItem]({%slug toolbar-items-button%}). All properties applicable for button toolbar item can be used in the navigation button toolbar item.

* `Items`(`IList<ToolbarItem>`)&mdash;Read-only collection of `Telerik.Maui.Controls.ToolbarItems` to navigate to in the toolbar.

* `Text`(`string`)&mdash;Defines the text(target type `Label`) in the toolbar item. You can display an image next to the text.
* `ImageSource`(`Microsoft.Maui.Controls.ImageSource`)&mdash;Specifies the source of the image to display in the toolbar item.

<snippet id='toolbar-navigationbutton-item'/>

## Events

The exposed events are:

* `Clicked`&mdash;Raised when the button is clicked.

## Commands

The available commands are:

* `Command`(`ICommand`)&mdash;Specifies the command to execute when the button is clicked.
* `CommandParameter`(`object`)&mdash;Specifies the parameter of the command, which is executed when the button is clicked.

## Styling

Use the `Style` property with target type `Telerik.Maui.Controls.NavigationButtonToolbarItemView`. Use all properties available for the [ButtonToolbarItemView]({%slug toolbar-items-button%}#styling), [LabelToolbarItemView]({%slug toolbar-items-label%}#styling) and [ToolbarItemView]({%slug toolbar-items%}#styling) in the `NavigationButtonToolbarItemView`.

## See Also

- [SplitButton ToolbarItem]({%slug toolbar-items-split-button%})
- [ToggleButton ToolbarItem]({%slug toolbar-items-toggle-button%})
- [Label ToolbarItem]({%slug toolbar-items-label%})
- [ListPicker ToolbarItem]({%slug toolbar-items-listpicker-button%})
- [Group ToolbarItem]({%slug toolbar-items-group%})
- [RadioButton ToolbarItem]({%slug toolbar-items-radio-button%})
- [Slider ToolbarItem]({%slug toolbar-items-slider%})