---
title: Range Thumb
page_title: .NET MAUI RangeSlider Documentation - Range Thumb
description: Learn how to use the range thumb that Telerik UI RangeSlider for .NET MAUI control provides.
position: 3
slug: rangeslider-range-thumb
---

# Range Thumb

Range thumb represents the start-end range inside the slider - it consists of the start thumb, the range track and the end thumb. 

The slider's range thumb is drawn corresponding to its `RangeStart` and `RangeEnd` values. Users can modify the range start value by dragging the start thumb, the end range value by dragging the end thumb, and both start and end simultenously by dragging the range track.

* `RangeStart`(`double`)&mdash;Specifies the start value of the range inside the slider.
* `RangeEnd`(`double`)&mdash;Specifies the end value of the range inside the slider.

Check a quick example on how to define `RangeStart` and `RangeEnd` properties:

<snippet id='rangeslider-getting-started-xaml' />

## Drag Mode

RangeSlider supports different dragging options&mdash;only the start thumb, only the end thumb, only the range track or any combination of them. In addition, you can completely disable the drag. 

You can control the available dragging options through the `DragMode` property of the RangeSlider:

* `DragMode`(`Telerik.Maui.Controls.RangeSlider.RangeSliderDragMode`)&mdash;Defines the available elemenents of the range thumb that can be dragged. You can choose from:
    * `Disabled`&mdash;drag is not enabled.
    * `StartThumb`&mdash;the start thumb can be dragged.
    * `RangeTrack`&mdash;the range track (the part between the start and end thumbs) can be dragged.
    * `EndThumb`&mdash;the end thumb can be dragged.

Check below some quick examples:

#### Only Range Thumbs:

<snippet id='rangeslider-drag-both-thumbs-xaml' />

#### Only Range Track:

<snippet id='rangeslider-drag-rangetrack-xaml' />

#### Disabled:

<snippet id='rangeslider-drag-disabled-xaml' />

## See Also

- [Visual Structure]({% slug rangeslider-visual-structure%})
- [Track Configuration]({% slug rangeslider-track-configuration%})
- [Range Thumb Styling]({% slug rangeslider-rangethumb-styling%})