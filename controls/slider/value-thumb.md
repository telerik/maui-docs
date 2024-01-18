---
title: Value Thumb
page_title: .NET MAUI Slider Documentation - Value Thumb
description: Learn how to use the value thumb that Telerik UI Slider for .NET MAUI control provides.
position: 3
slug: slider-value-thumb
---

# Value Thumb

The slider's value thumb is drawn corresponding to its `Value` property. Users can modify the `Value` by dragging the thumb along the backtrack or touching anywhere on the slider (the thumb, or the range track, or the backtrack) depending on the selected drag mode.

* `Value`(`double`)&mdash;Specifies the selected value of the slider, corresponds to the thumb position across the backtrack.

Check a quick example on how to define `Value` property:

<snippet id='slider-getting-started-xaml' />

## Drag Mode

The Slider supports different dragging options&mdash;only the thumb or free. In addition, you can completely disable the drag. 

You can control the available dragging options through the `DragMode` property of the Slider:

* `DragMode`(`Telerik.Maui.Controls.Slider.SliderDragMode`)&mdash;Defines the possible ways to interact with the Slider and change its `Value`. You can choose from:
    * `Disabled`&mdash;drag is not enabled.
    * `Thumb`&mdash;the thumb can be dragged.
    * `Free`&mdash;touching anywhere (the thumb, or the range track, or the backtrack) will lead to the `Value` being changed.
 
Check below some quick examples:

#### Only Thumb:

<snippet id='slider-drag-thumb-xaml' />

#### Free:

<snippet id='slider-drag-free-xaml' />

#### Disabled:

<snippet id='slider-drag-disabled-xaml' />

## See Also

- [Visual Structure]({% slug slider-visual-structure%})
- [Backtrack Configuration]({% slug slider-backtrack-configuration%})
- [Thumb Styling]({% slug slider-thumb-styling%})