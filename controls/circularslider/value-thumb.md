---
title: Value Thumb
page_title: .NET MAUI CircularSlider Documentation - Value Thumb
description: Learn how to use the value thumb of the Telerik UI CircularSlider for .NET MAUI. End users drag the value thumb along the arc to select a desired value.
position: 5
slug: circularslider-value-thumb
---

# .NET MAUI CircularSlider Value Thumb

The CircularSlider's value thumb is drawn based on its `Value` property. End users can modify the `Value` by dragging the thumb along the backtrack or touching anywhere on the slider (the thumb, the range track, or the backtrack) depending on the drag mode (configured with the `DragMode` property).

* `Value` (`double`)&mdash;Specifies the selected value of the slider, corresponds to the thumb position across the backtrack.

Here is a quick example on how to define the `Value` property:

<snippet id='circularslider-value-xaml' />

## Drag Mode

The CircularSlider's `DragMode` property lets you configure one of three dragging options&mdash;only the thumb, free, or disabled.

* `DragMode` (`Telerik.Maui.Controls.Sliders.SliderDragMode`)&mdash;Defines the possible ways to interact with the CircularSlider and change its `Value`. You can choose from:
    * `Thumb`&mdash;The thumb moves along the backtrack only by dragging.
    * `Free`&mdash;The thumb's position (and the `Value` property) changes via dragging or touching anywhere on the range track or backtrack.
    * `Disabled`&mdash;The thumb's position is fixed on the backtrack and dragging is disabled.

Check below some quick examples:

>caption Example with DragMode set to Only Thumb

<snippet id='circularslider-drag-thumb-xaml' />

>caption Example with DragMode set to Free

<snippet id='circularslider-drag-free-xaml' />

>caption Example with DragMode set to Disabled

<snippet id='circularslider-drag-disabled-xaml' />

## See Also

- [Visual Structure]({% slug circularslider-visual-structure%})
- [Backtrack]({% slug circularslider-backtrack%})
- [Thumb Styling]({% slug circularslider-thumb-styling%})
