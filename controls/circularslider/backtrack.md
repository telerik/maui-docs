---
title: Backtrack
page_title: .NET MAUI CircularSlider Documentation - Backtrack
description: Learn how to configure the backtrack of the Telerik UI CircularSlider for .NET MAUI - set the min and max values and choose if the backtrack should extend beyond them.
position: 6
slug: circularslider-backtrack
---

# .NET MAUI CircularSlider Backtrack

The thumb runs along the backtrack of the CircularSlider. The backtrack represents all the values your end users can choose from.

## Minimum and Maximum

You need to configure a `Minimum` value and a `Maximum` value for the CircularSlider. These values define the limits of the backtrack.

* `Minimum` (`double`)&mdash;Defines the minimum value of the slider.
* `Maximum` (`double`)&mdash;Defines the maximum value of the slider.

<snippet id='circularslider-getting-started-xaml' />

## Backtrack Extent

By default, the backtrack is drawn between the `Minimum` and `Maximum` values. Through the `BackTrackExtent` property you can extend the backtrack at the edges beyond the minimum and the maximum values.

* `BackTrackExtent` (`double`)&mdash;Defines how many pixels beyond the minimum and the maximum values the backtrack extends.

## See Also

* [Value Thumb]({% slug circularslider-value-thumb%})
* [Range Track]({%slug circularslider-range-track%})
* [Track Styling]({% slug circularslider-track-styling%})
