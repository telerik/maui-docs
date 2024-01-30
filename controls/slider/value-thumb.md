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

* `DragMode`(`Telerik.Maui.Controls.Sliders.SliderDragMode`)&mdash;Defines the possible ways to interact with the Slider and change its `Value`. You can choose from:
    * `Thumb`&mdash;The thumb moves along the backtrack only by dragging.
    * `Free`&mdash;The thumb's position (and the `Value` property) changes via dragging or touching anywhere on the range track or backtrack.
    * `Disabled`&mdash;The thumb's position is fixed on the backtrack and dragging is disabled.
 
Check below some quick examples:

#### Only Thumb

<snippet id='slider-drag-thumb-xaml' />

#### Free

<snippet id='slider-drag-free-xaml' />

#### Disabled

<snippet id='slider-drag-disabled-xaml' />

## See Also

- [Visual Structure]({% slug slider-visual-structure%})
- [Backtrack]({% slug slider-backtrack%})
- [Thumb Styling]({% slug slider-thumb-styling%})
