---
title: Track Styling
page_title: .NET MAUI RangeSlider Documentation - Track Styling
description: Review the styling options that the Telerik UI for .NET MAUI RangeSlider control provides for its track.
position: 1
slug: rangeslider-track-styling
---

# Track Styling

The RangeSlider for .NET MAUI control exposes thickness and color styling properties for its range track (between the start thumb and end thumb) as well as its backtrack (the track the range thumb slides along), so you can easily achieve the desired look & feel:

* `BackTrackThickness`(`double`)&mdash;Specifies the thickness of the range slider's backtrack.
* `BackTrackColor`(`Color`)&mdash;Defines the color of the range slider's backtrack.
* `BackTrackStyle`(`Style`)&mdash;Sets a custom style to the range slider's backtrack.

Check the following stype properties related to the range track (part of the range thumb):

* `RangeTrackFill`(`Color`)&mdash;Defines fill color to the range track.
* `RangeTrackStyle`(`Style`)&mdash;Applies a custom style to the range track.

Here is a  a quick example on how to apply the range/backtrack properties to the RangeSlider:

**1.** Add a custom style with `TargetType` set to `RadBorder` to the page's resources:

<snippet id='rangeslider-track-style' />

**2.** Add a custom style with `TargetType` set to `SliderRangeTrack` to the page's resources:

<snippet id='rangeslider-rangetrack-style' />

**3.** Define the RangeSlider with the styles applied:

<snippet id='rangeslider-track-style-xaml' />

Check the result below:

![Telerik RangeSlider for .NET MAUI Track Styling](images/rangeslider-track-styling.png)

## See Also

- [Track Configuration]({% slug rangeslider-track-configuration%})
- [Range Thumb]({% slug rangeslider-range-thumb%})