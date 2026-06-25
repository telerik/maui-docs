---
title: Track Configuration
page_title: .NET MAUI RangeSlider Documentation - Track Configuration
description: Learn how to use the track configuration options that Telerik UI RangeSlider for .NET MAUI control provides.
position: 4
slug: rangeslider-track-configuration
---

# Track Configuration

The track refers to that part of the range slider the range thumb runs along. It represents all the range values users can choose from.

## Minimum and Maximum

You need to configure a `Minimum` value and a `Maximum` value for the RangeSlider, which define the limits of the range slider’s track.

* `Minimum` (`double`)&mdash;Defines the minimum value of the range slider.
* `Maximum` (`double`)&mdash;Specifies the maximum value of the range slider.
* `BackTrackExtent` (`double`)&mdash;Defines how many pixels beyond the minimum and the maximum values the backtrack extends.

<snippet id='rangeslider-getting-started-xaml' />

## See Also

* [Range Thumb]({% slug rangeslider-range-thumb%})
* [Track Styling]({% slug rangeslider-track-styling%})