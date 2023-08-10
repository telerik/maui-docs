---
title: ListPickerButton
page_title: .NET MAUI Toolbar Documentation - ListPickerButton ToolbarItem
description: Review the Toolbar list picker button item for .NET MAUI.
position: 5
slug: toolbar-items-listpicker-button
---

# .NET MAUI ListPickerButton ToolbarItem

Add a list picker toolbar item using the `ListPickerButtonToolbarItem`.

The exposed properties are:

* `ItemsSource`(`IList`)&mdash;Specifies a collection of items to display in the list.
* `ItemTemplate`(`DataTemplate`)&mdash;Specifies the `DataTemplate` used to generate content for the list items.
* `SelectedItem`(`object`)&mdash;Specifies the currently selected item in the list.
* `Text`(`string`)&mdash;Defines the text(target type `Label`) in the toolbar item. You can display an image next to the text.
* `ImageSource`(`Microsoft.Maui.Controls.ImageSource`)&mdash;Specifies the source of the image to display in the toolbar item.

## Events

The exposed events are:

* `SelectionChanged`&mdash;Raised when the current selection has changed.
* `Clicked`&mdash;Raised when the toolbar item is clicked.

## Commands

The available commands are:

* `Command`(`ICommand`)&mdash;Specifies the command to execute when the toolbar item is clicked.
* `CommandParameter`(`object`)&mdash;Specifies the parameter of the command, which is executed when the toolbar item is clicked.

## Styling

Style the `ListPickerButtonToolbarItem` using the following properties:

* `ItemStyle`(`Style`)&mdash;Specifies the style applied to the list items. The target type of this style is `Telerik.Maui.Controls.ToolbarListItemView`.
* `Style`(`Style`)&mdash;Specifies the style applied to the list items. The target type of this style is `Telerik.Maui.Controls.ListPickerButtonToolbarItemView`. The available properties are:
	* `ItemTemplate`(`DataTemplate`)&mdash;Specifies the `DataTemplate` used to generate content for the list items.
	* `SelectedItem`(`object`)&mdash;Specifies the currently selected item in the list
	* `ItemStyle`(`Style`)&mdash;Specifies the style applied to the list items. The target type of this style is `Telerik.Maui.Controls.ToolbarListItemView`.
	* `ItemsSource`(`IList`)&mdash;Specifies a collection of items to display in the list.
    * All properties applicable in [DropDownButtonToolbarItemView]({%slug toolbar-items-dropdown-button%}#styling), [ButtonToolbarItemView]({%slug toolbar-items-button%}#styling), [ToolbarItemView]({%slug toolbar-items%}#styling) and [LabelToolbarItemView]({%slug toolbar-items-label%}#styling).

## See Also

- [SplitButton ToolbarItem]({%slug toolbar-items-split-button%})
- [ToggleButton ToolbarItem]({%slug toolbar-items-toggle-button%})
- [Label ToolbarItem]({%slug toolbar-items-label%})
- [NavigationButton ToolbarItem]({%slug toolbar-items-navigation-button%})
- [Group ToolbarItem]({%slug toolbar-items-group%})
- [RadioButton ToolbarItem]({%slug toolbar-items-radio-button%})
- [Slider ToolbarItem]({%slug toolbar-items-slider%})