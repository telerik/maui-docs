---
title: Track Styling
page_title: .NET MAUI RangeSlider Documentation - Track Styling
description: Review the styling options that the Telerik UI for .NET MAUI RangeSlider control provides for its track.
position: 1
slug: rangeslider-track-styling
---

# Track Styling

The RangeSlider for .NET MAUI control exposes thickness and color styling properties for its track, so you can easily achieve the desired look&feel:

* `BackTrackThickness(double)`&mdash;Specifies the thickness of the range slider's track.
* `BackTrackColor(Color)`&mdash;Defines the color of the range slider's track.
* `BackTrackStyle(Style)`&mdash;Sets a custom style to the range slider's track.

Check below a quick example on how to apply `BacktrackStyle` property to the RangeSlider:

**1.** Add The custom style with `TargetType` set to `RadBorder` to the page's resources:

<snippet id='rangeslider-track-style' />

**2.** Define the RangeSlider with the style applied:

<snippet id='rangeslider-track-style-xaml' />

## See Also

- [Track Configuration]({% slug rangeslider-track-configuration%})
- [Range Thumb]({% slug rangeslider-range-thumb%})