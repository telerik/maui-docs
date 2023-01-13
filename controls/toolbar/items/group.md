---
title: Group
page_title: .NET MAUI Toolbar Documentation - Group ToolbarItem
description: "Review the Toolbar group item for .NET MAUI"
position: 0
slug: toolbar-items-group
---

# .NET MAUI Group ToolbarItem

Represents a group of toolbar items in the Toolbar control. The group works as a container of its child toolbar items keeping them in one place. For instance, when the group does not fit in the main strip area of the toolbar, all child toolbar items are moved to the overflow area together.

Another use is to create two or more independent sets of radio buttons in the toolbar. Normally, only one radio button can be selected at a time. To create independent sets of radio buttons, they can be placed in separate groups.

The exposed property is: 

* `Items`(`IList<ToolbarItem>`)&mdash;Read-only collection of `Telerik.Maui.Controls.ToolbarItems` to display in the group.

## Styling 

GroupToolbarItem has a `Style` property with target type `GroupToolbarItemView`. The properties exposed in the `GroupToolbarItem` are:

* `ItemSpacing`(`double`)&mdash;Specifies the spacing in pixels between the toolbar items in the group.
* `ItemsSource`(`IList`)&mdash;Specifies a collection of toolbar items to be placed in the group.

All other properties that can be applied through style are the properties exposed for [ToolbarItemView]({%slug toolbar-items%}#styling).


## See Also

- [SplitButton ToolbarItem]({%slug toolbar-items-split-button%})
- [ToggleButton ToolbarItem]({%slug toolbar-items-toggle-button%})
- [Label ToolbarItem]({%slug toolbar-items-label%})
- [NavigationButton ToolbarItem]({%slug toolbar-items-navigation-button%})
- [ListPicker ToolbarItem]({%slug toolbar-items-listpicker-button%})
- [RadioButton ToolbarItem]({%slug toolbar-items-radio-button%})
- [Slider ToolbarItem]({%slug toolbar-items-slider%})