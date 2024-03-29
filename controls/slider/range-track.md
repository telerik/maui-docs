---
title: Range Track
page_title: .NET MAUI Slider Documentation - Range Track
description: Learn how to configure the range track of the Telerik UI Slider for .NET MAUI.
position: 6
slug: slider-range-track
---

# .NET MAUI Slider Range Track

The range track refers to that part of the backtrack between the Slider's `OriginValue` and the currently set `Value`.

By default, the range track starts at the backtrack minimum and runs along to the value thumb's position. You can define a different initial position of the range track through the Slider's `OriginValue` property:

* `OriginValue`(`double`)&mdash;Specifies the value across the backtrack where the range track starts.

Check a quick example on how to define the `OriginValue` property, so that the range track starts at the center of the backtrack:

<snippet id='slider-range-track-xaml' />

![Telerik Slider for .NET MAUI Range Track](images/slider-range-track.png)

## See Also

- [Visual Structure]({% slug slider-visual-structure%})
- [Backtrack]({% slug slider-backtrack%})
- [Thumb Styling]({% slug slider-thumb-styling%})
- [Track Styling]({% slug slider-track-styling %})
