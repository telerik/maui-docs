---
title: Thumb Styling
page_title: .NET MAUI Slider Documentation - Thumb Styling
description: Learn how to style the thumb of the Telerik UI for .NET MAUI Slider. Explore an example that creates consistent styling for the thumb and the range track.
position: 0
slug: slider-thumb-styling
---

# .NET MAUI Slider Thumb Styling

The Slider for .NET MAUI provides the following styling options for the value thumb:

* `ThumbFill`(`Color`)&mdash;Defines the fill color of the Slider's thumb.
* `ThumbStyle`(`Style`)&mdash;Defines a custom style for the Slider's thumb.

In addition, you can modify the look and feel of the range track, so it matches the style of the thumb. Range track refers to that part of the backtrack from the Slider's `OriginValue` along to the position of the value thumb. 

* `RangeTrackFill`(`Color`)&mdash;Defines the fill color of the Slider's range track.
* `RangeTrackStyle`(`Style`)&mdash;Defines a custom style for the Slider's range track.

The following example demonstrates how to use the described styling properties to style the Slider's thumb and range track:

**1.** Add the styles to the page resources:

<snippet id='slider-value-elements-styling' />

**2.** Apply them to the Slider:

<snippet id='slider-value-elements-styling-xaml' />

Check the result below:

![Telerik Slider for .NET MAUI Value Thumb Styling](images/slider-thumb-styling.png)

## See Also

- [Visual Structure]({% slug slider-visual-structure%})
- [Value Thumb]({% slug slider-value-thumb%})
- [Range Track]({%slug slider-range-track%})