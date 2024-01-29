---
title: Value Thumb
page_title: .NET MAUI Slider Documentation - Value Thumb
description: Learn how to use the value thumb of the Telerik UI Slider for .NET MAUI. End users drag the value thumb across the backtrack to select a desired value.
position: 4
slug: slider-value-thumb
---

# .NET MAUI Slider Value Thumb

The Slider's value thumb is drawn based on its `Value` property. End users can modify the `Value` by dragging the thumb along the backtrack or touching anywhere on the slider (the thumb, the range track, or the backtrack) depending on the drag mode (configured with the `DragMode` property).

* `Value`(`double`)&mdash;Specifies the selected value of the slider, corresponds to the thumb position across the backtrack.

Check a quick example on how to define the `Value` property:

<snippet id='slider-getting-started-xaml' />

## Drag Mode

The Slider's `DragMode` property lets you configure one of three dragging options&mdash;only the thumb, free, or disabled.

You can control the available dragging options through the `DragMode` property of the Slider:

* `DragMode`(`Telerik.Maui.Controls.Slider.SliderDragMode`)&mdash;Defines the possible ways to interact with the Slider and change its `Value`. You can choose from:
    * `Disabled`&mdash;drag is not enabled.
    * `Thumb`&mdash;The thumb moves along the backtrack only by dragging.
    * `Free`&mdash;touching anywhere (the thumb, or the range track, or the backtrack) will lead to the `Value` being changed.
 
Check below some quick examples:

#### Only Thumb

<snippet id='slider-drag-thumb-xaml' />

#### Free

<snippet id='slider-drag-free-xaml' />

#### Disabled

<snippet id='slider-drag-disabled-xaml' />

## See Also

- [Visual Structure]({% slug slider-visual-structure%})
- [Backtrack Configuration]({% slug slider-backtrack-configuration%})
- [Thumb Styling]({% slug slider-thumb-styling%})
