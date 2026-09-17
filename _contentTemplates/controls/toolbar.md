#toolbar-styling
Style the toolbar items using the `Style`(`Style`) property. Each toolbar item has a corresponding `ToolbarItemView` and this is the target type of the Style property.

| Toolbar Item | Style Target Type |
| ------------ | ------- |
| [`ToolbarItem`]({%slug toolbar-items%}) | `ToolbarItemView` |
| [`EntryToolbarItem`]({%slug toolbar-items-entry%}) | `entryToolbarItemView` |
| [`ButtonToolbarItem`]({%slug toolbar-items-button%}) | `ButtonToolbarItemView` |
| [`DropDownButtonToolbarItem`]({%slug toolbar-items-dropdown-button%}) | `DropDownButtonToolbarItemView` |
| [`DropDownMenuButtonToolbarItem`]({%slug toolbar-items-dropdown-button%}) | `DropDownMenuButtonToolbarItemView` |
| [`ToggleButtonToolbarItem`]({%slug toolbar-items-toggle-button%}) | `ToggleButtonToolbarItemView` |
| [`RadioButtonToolbarItem`]({%slug toolbar-items-radio-button%}) | `RadioButtonToolbarItemView` |
| [`NavigationButtonToolbarItem`]({%slug toolbar-items-navigation-button%}) | `NavigationButtonToolbarItemView` |
| [`SplitButtonToolbarItem`]({%slug toolbar-items-split-button%}) | `SplitButtonToolbarItemView` |
| [`OptionsButtonToolbarItem`]({%slug toolbar-items-overflow%}) | `OptionsButtonToolbarItemView` |
| [`SliderToolbarItem`]({%slug toolbar-items-slider%}) | `SliderToolbarItemView` |
| [`ListPickerButtonToolbarItem`]({%slug toolbar-items-listpicker-button%}) | `ToolbarListItemView` |
| [`LabelToolbarItem`]({%slug toolbar-items-label%}) | `LabelToolbarItemView` |
| [`BusyIndicatorToolbarItem`]({%slug toolbar-items-busyindicator%}) | `BusyIndicatorToolbarItemView` |
| [`SeparatorToolbarItem`]({%slug toolbar-items-separator%}) | `SeparatorToolbarItemView` |
| [`GroupToolbarItem`]({%slug toolbar-items-group%}) | `GroupToolbarItemView` |

Common properties that can be applied to the Style of each toolbar item are: 

* `Orientation`(enum of type `Telerik.Maui.Controls.ToolbarOrientation`)&mdash;Specifies the orientation of the toolbar item in the toolbar. The available options are:
	* `Horizontal`
	* `Vertical`


* `PlacementLocation`(enum of type `Telerik.Maui.Controls.ToolbarItemPlacementOptions`)&mdash;Specifies the placement location of the toolbar item in the toolbar. This type supports a bitwise combination of its members to enable more than one option. The available options are:
	* `ToolStrip`&mdash;The toolbar item appears in the main tool strip area of the toolbar.
	* `DropDown`&mdash;The toolbar item appears in the overflow drop-down menu of the toolbar.

* `ControlTemplate`(`Microsoft.Maui.Controls.ControlTemplate`)&mdash;Specifies the control template of the toolbar item.
* `BackgroundColor`(`Microsoft.Maui.Graphics.Color`)&mdash;Specifies the background color of the toolbar item.
* `BorderColor`(`Microsoft.Maui.Graphics.Color`)&mdash;Specifies the border color of the toolbar item.
* `BorderThickness`(`Microsoft.Maui.Thickness`)&mdash;Specifies the border thickness of the toolbar item.
* `CornerRadius`(`Microsoft.Maui.Thickness`)&mdash;Specifies the corner radius of the toolbar item.
* `ContentPadding`(`Microsoft.Maui.Thickness`)&mdash;Specifies the content padding of the control.
#end