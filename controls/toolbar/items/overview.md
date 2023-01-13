---
title: Overview
page_title: .NET MAUI Toolbar Documentation - Overview
description: "Review the Toolbar item for .NET MAUI"
position: 0
slug: toolbar-items
---

# .NET MAUI ToolbarItem Overview

Telerik .NET MAUI Toolbar provides a built-in toolbar items. The availabler items are descirbed in the table below: 

| Toolbar Item | Description |
| ------------ | ------- |
| `ToolbarItem` | Represents a toolbar item in the Toolbar control. All toobar items listed below inherits from `ToolbarItem` |
| `ButtonToolbarItem` | Represents a button in the Toolbar control. |
| `DropDownButtonToolbarItem` | Represents a button displaying a drop-down panel in the Toolbar control. |
| `DropDownMenuButtonToolbarItem` | Represents a button displaying a drop-down menu in the Toolbar control. |
| `ToggleButtonToolbarItem` | Represents a toggle button in the Toolbar control. |
| `RadioButtonToolbarItem` | Represents a radio button in the Toolbar control. |
| `NavigationButtonToolbarItem` | Represents a navigation button in the Toolbar control. |
| `SplitButtonToolbarItem` | Represents a split button in the Toolbar control. Works as an advanced drop-down menu. |
| `OptionsButtonToolbarItem` | Represents a button displaying an options panel in the RadToolbar control. |
| `SliderToolbarItem` | Represents a slider in the Toolbar control |
| `ListPickerButtonToolbarItem` | Represents a list picker button in the Toolbar control. |
| `LabelToolbarItem` | Represents a label in the Toolbar control. The label can display a text and optionally an image next to it. |
| `SeparatorToolbarItem` | Represents a separator(which is an UI element) in the Toolbar control. |
| `GroupToolbarItem` | Organize toolbar items in a group. |

In additon you can define an option panel in the toolbar using the `RadToolbarOptionsPanel`.

## Common properties for configuration 

All toolbar items inherits from `ToolbarItem`. The available properties ToolbarItem provides are:

* `IsVisible`(`bool`)&mdash;Specifies whether the toolbar item is visible.
* `IsEnabled`(`bool`)&mdash;Specifies whether the toolbar item is enabled.
* `Style`(`Style`)&mdash;Specifies the style applied to the toolbar item. Each toolbar item has a corresponding ToolbarItemView. And this is the target type of the Style.

For example the target type for `ButtonToolbarItem` `Style` is `ButtonToolbarItemView`.

* `ControlTemplate`(`Microsoft.Maui.Controls.ControlTemplate`)&mdash;Specifies the template applied to the toolbar item. Each toolbar item has a corresponding ToolbarItemView. And this is the target type of the ControlTemplate.

* `PlacementOptions`(enum of type `Telerik.Maui.Controls.ToolbarItemPlacementOptions`)&mdash;Defines the allowed placement options of the toolbar item in the toolbar. This type supports a bitwise combination of its members to enable more than one option. The available options are:
	* `ToolStrip`&mdash;The toolbar item appears in the main tool strip area of the toolbar.
	* `DropDown`&mdash;The toolbar item appears in the overflow drop-down menu of the toolbar.

## Styling

Style the toolbar items using the `Style`(`Style`) property. Each toolbar item has a corresponding ToolbarItemView and this is the target type of the Style property.


| Toolbar Item | Style Target Type |
| ------------ | ------- |
| `ToolbarItem` | `ToolbarItemView` |
| `ButtonToolbarItem` | `ButtonToolbarItemView` |
| `DropDownButtonToolbarItem` | `DropDownButtonToolbarItemView` |
| `DropDownMenuButtonToolbarItem` | `DropDownMenuButtonToolbarItemView` |
| `ToggleButtonToolbarItem` | `ToggleButtonToolbarItemView` |
| `RadioButtonToolbarItem` | `RadioButtonToolbarItemView` |
| `NavigationButtonToolbarItem` | `NavigationButtonToolbarItemView` |
| `SplitButtonToolbarItem` | `SplitButtonToolbarItemView` |
| `OptionsButtonToolbarItem` | `OptionsButtonToolbarItemView` |
| `SliderToolbarItem` | `SliderToolbarItemView` |
| `ListPickerButtonToolbarItem` | `ToolbarListItemView` |
| `LabelToolbarItem` | `LabelToolbarItemView` |
| `SeparatorToolbarItem` | `SeparatorToolbarItemView` |
| `GroupToolbarItem` | `GroupToolbarItemView` |

Common properties that can be applied to the Style of each toolbar item are: 

* `Orientation`(enum of type `Telerik.Maui.Controls.ToolbarOrientation`)&mdash;Specifies the orientation of the toolbar item in the toolbar. The available options are:
	* `Horizontal`
	* `Vertical`


* `PlacementLocation`(enum of type `Telerik.Maui.Controls.ToolbarItemPlacementOptions`)&mdash;Specifies the placement location of the toolbar item in the toolbar. This type supports a bitwise combination of its members to enable more than one option. The available options are:
	* `ToolStrip`&mdash;The toolbar item appears in the main tool strip area of the toolbar.
	* `DropDown`&mdash;The toolbar item appears in the overflow drop-down menu of the toolbar.

## See Also

