---
title: Thumb Styling
page_title: .NET MAUI CircularSlider Documentation - Thumb Styling
description: Learn how to style the thumb of the Telerik UI for .NET MAUI CircularSlider. Explore an example that creates consistent styling for the thumb and the range track.
position: 0
slug: circularslider-thumb-styling
---

# .NET MAUI CircularSlider Thumb Styling

The CircularSlider for .NET MAUI provides the following styling options for the value thumb:

* `ThumbFill` (`Color`)&mdash;Defines the fill color of the CircularSlider's thumb.
* `ThumbStyle` (`Style` with target type `Telerik.Maui.Controls.RangeSlider.SliderThumb`)&mdash;Defines a custom style for the CircularSlider's thumb.

In addition, you can modify the look and feel of the range track, so it matches the style of the thumb. Range track refers to that part of the backtrack from the CircularSlider's `OriginValue` along to the position of the value thumb.

* `RangeTrackFill` (`Color`)&mdash;Defines the fill color of the CircularSlider's range track.
* `RangeTrackStyle` (`Style`)&mdash;Defines a custom style for the CircularSlider's range track.

The following example demonstrates how to use the described styling properties to style the CircularSlider's thumb and range track:

1. Add the styles to the page resources:

<snippet id='circularslider-value-elements-styling' />

2. Apply them to the CircularSlider:

<snippet id='circularslider-value-elements-styling-xaml' />

![Telerik CircularSlider for .NET MAUI Value Thumb Styling](images/circularslider-thumb-styling.png)

## See Also

- [Visual Structure]({% slug circularslider-visual-structure%})
- [Value Thumb]({% slug circularslider-value-thumb%})
- [Range Track]({%slug circularslider-range-track%})
