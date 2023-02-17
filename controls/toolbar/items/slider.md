---
title: Slider
page_title: .NET MAUI Toolbar Documentation - Slider
description: "Review the Toolbar Slider item for .NET MAUI"
position: 8
slug: toolbar-items-slider
---

# .NET MAUI Toolbar Slider

You can add a slider in the Toolbar control using the `SliderToolbarItem`.

The available properties for configuration are:

* `Value`(`double`)&mdash;Specifies the value of the slider.
* `Minimum`(`double`)&mdash;Specifies the minimum value of the slider.
* `Maximum`(`double`)&mdash;Specifies the maximum value of the slider.

<snippet id='toolbar-slider-item'/>

## Events

* `ValueChanged`&mdash;Raised when the `SliderToolbarItem.Value` property has changed.

## Styling

SliderToolbarItem has the following styling properties:

* `SliderStyle`(`Style` with target type `Microsoft.Maui.controls.Slider`)&mdash;Specifies the style of the slider.
* `Style`(`Style` with target type `Telerik.Maui.Controls.SliderToolbarItemView`). The available properies are:
	* `Value`(`double`)&mdash;Specifies the value of the slider.
	* `Minimum`(`double`)&mdash;Specifies the minimum value of the slider.
	* `Maximum`(`double`)&mdash;Specifies the maximum value of the slider.
	* `SliderStyle`(`Style` with target type `Microsoft.Maui.controls.Slider`)&mdash;Specifies the style of the slider.

All other properties that can be applied through style are the properties applicable for [ToolbarItemView]({%slug toolbar-items%}#styling).

## See Also

- [SplitButton ToolbarItem]({%slug toolbar-items-split-button%})
- [ToggleButton ToolbarItem]({%slug toolbar-items-toggle-button%})
- [Label ToolbarItem]({%slug toolbar-items-label%})
- [NavigationButton ToolbarItem]({%slug toolbar-items-navigation-button%})
- [ListPicker ToolbarItem]({%slug toolbar-items-listpicker-button%})
- [Group ToolbarItem]({%slug toolbar-items-group%})
- [RadioButton ToolbarItem]({%slug toolbar-items-radio-button%})

