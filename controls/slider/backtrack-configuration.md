---
title: Backtrack Configuration
page_title: .NET MAUI Slider Documentation - Backtrack Configuration
description: Learn how to use the backtrack configuration options that Telerik UI Slider for .NET MAUI control provides.
position: 4
slug: slider-backtrack-configuration
---

# Backtrack Configuration

The backtrack refers to that part of the slider the thumb runs along. It represents all the values users can choose from.

## Minimum and Maximum

You need to configure a `Minimum` value and a `Maximum` value for the Slider, which define the limits of the slider’s backtrack.

* `Minimum`(`double`)&mdash;Defines the minimum value of the slider.
* `Maximum`(`double`)&mdash;Specifies the maximum value of the slider.

<snippet id='slider-getting-started-xaml' />

## Backtrack Extent

By default the backtrack is drawn between the `Minimum` and `Maximum` values. Through the `BacktrackExtent` property you can extend the backtrack at the edges beyond the min and the max values.

* `BacktrackExtent`(`double`)&mdash;Defines the pixel length that the backtrack extends beyond the min and the max values.

```XAML
 <telerik:RadSlider Minimum="0"
                    Maximum="100"
                    Value="35"
                    TickStep="10"
                    TicksPlacement="End"
                    LabelStep="100"
                    LabelsPlacement="End"
                    BackTrackExtent="50"/>
```

![Telerik Slider for .NET MAUI Backtrack Extent](images/slider-backtrack-extent.png)

## See Also

* [Value Thumb]({% slug slider-value-thumb%})
* [Track Styling]({% slug slider-track-styling%})
