---
title: SplitButton
page_title: .NET MAUI Toolbar Documentation - SplitButton ToolbarItem
description: Review the Toolbar split button item for .NET MAUI.
position: 5
slug: toolbar-items-split-button
---

# .NET MAUI SplitButton ToolbarItem

Add a split button in the toolbar using the `SplitButtonToolbarItem`. The toolbar item inherits from the `DropDownMenuButtonToolbarItem`.

The exposed property is `Items`(of type `IList<ToolbarItem>`)&mdash;Read-only collection of `ToolbarItems` to display in the drop-down menu.

>important `DropDownMenuButtonToolbarItem` inherits from `DropDownButtonToolbarItem`. You can apply all properties from the `DropDownButtonToolbarItem` to the `SplitButtonToolbarItem`. The properties are described in the [DropDownButton ToolbarItem]({%slug toolbar-items-dropdown-button%}) article.

<snippet id='toolbar-splitbutton-item'/>

## Styling

`SplitButtonToolbarItem` has `Style` property with target type `SplitButtonToolbarItemView`.

The properties that can be applied through style are the properties applicable for [DropDownButtonToolbarItemView]({%slug toolbar-items-dropdown-button%}#styling), [ButtonToolbarItemView]({%slug toolbar-items-button%}#styling), [ToolbarItemView]({%slug toolbar-items%}#styling) and [LabelToolbarItemView]({%slug toolbar-items-label%}#styling).

## See Also

- [ToggleButton ToolbarItem]({%slug toolbar-items-toggle-button%})
- [Label ToolbarItem]({%slug toolbar-items-label%})
- [NavigationButton ToolbarItem]({%slug toolbar-items-navigation-button%})
- [ListPicker ToolbarItem]({%slug toolbar-items-listpicker-button%})
- [Group ToolbarItem]({%slug toolbar-items-group%})
- [RadioButton ToolbarItem]({%slug toolbar-items-radio-button%})
- [Slider ToolbarItem]({%slug toolbar-items-slider%})