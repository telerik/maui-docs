---
title: Range Track
page_title: .NET MAUI Slider Documentation - Range Track
description: Learn how to use the Range Track that Telerik UI Slider for .NET MAUI control provides.
position: 4
slug: slider-range-track
---

# Range Track

The range track refers to that part of the backtrack between Slider's `OriginValue` and `Value`.

In the common case the range track starts at the backtrack minimum and runs along to the value thumb. You can define a different initial position of the range track through the Slider's `OriginValue` property:

* `OriginValue`(`double`)&mdash;Specifies the value across the backtrack where the range track starts.

Check a quick example on how to define `OriginValue` property, so that the range track starts at the center of the backtrack:

<snippet id='slider-range-track-xaml' />

![Telerik Slider for .NET MAUI Range Track](images/slider-range-track.png)

## See Also

- [Visual Structure]({% slug slider-visual-structure%})
- [Backtrack Configuration]({% slug slider-backtrack-configuration%})
- [Thumb Styling]({% slug slider-thumb-styling%})
- [Track Styling]({% slug slider-track-styling %})