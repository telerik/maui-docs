---
title: Track Styling
page_title: .NET MAUI Slider Documentation - Track Styling
description: Review the styling options that the Telerik UI for .NET MAUI Slider control provides for its backtrack and range track.
position: 1
slug: slider-track-styling
---

# Track Styling

The Slider for .NET MAUI control exposes thickness and color styling properties for its range track (between `Minimum` and `Value`) as well as its backtrack (the track the thumb slides along), so you can easily achieve the desired look & feel:

* `BackTrackThickness`(`double`)&mdash;Specifies the thickness of the slider's backtrack.
* `BackTrackColor`(`Color`)&mdash;Defines the color of the slider's backtrack.
* `BackTrackStyle`(`Style`)&mdash;Sets a custom style to the slider's backtrack.

Check the following stype properties related to the range track (part of the backtrack between the `Minimum` and `Value`):
 
* `RangeTrackFill`(`Color`)&mdash;Defines fill color to the range track.
* `RangeTrackStyle`(`Style`)&mdash;Applies a custom style to the range track.

Here is a  a quick example on how to apply the range/backtrack properties to the Slider:

**1.** Add a custom style with `TargetType` set to `RadBorder` to the page's resources:

<snippet id='slider-backtrack-style' />

**2.** Add a custom style with `TargetType` set to `SliderRangeTrack` to the page's resources:

<snippet id='slider-rangetrack-style' />

**3.** Define the Slider with the styles applied:

<snippet id='slider-track-style-xaml' />

Check the result below:

![Telerik Slider for .NET MAUI Track Styling](images/slider-track-styling.png)

## See Also

- [Backtrack Configuration]({% slug slider-backtrack-configuration%})
- [Value Thumb]({% slug slider-value-thumb%})