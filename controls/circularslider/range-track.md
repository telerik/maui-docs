---
title: Range Track
page_title: .NET MAUI CircularSlider Documentation - Range Track
description: Learn how to configure the range track of the Telerik UI CircularSlider for .NET MAUI.
position: 7
slug: circularslider-range-track
---

# .NET MAUI CircularSlider Range Track

The range track refers to that part of the backtrack between the CircularSlider's `OriginValue` and the currently set `Value`.

By default, the range track starts at the backtrack minimum and runs along to the value thumb's position. You can define a different initial position of the range track through the CircularSlider's `OriginValue` property:

* `OriginValue` (`double`)&mdash;Specifies the value across the backtrack where the range track starts.

Here is a quick example on how to define the `OriginValue` property, so that the range track starts at the center of the backtrack:

<snippet id='circularslider-range-track-xaml' />

![Telerik CircularSlider for .NET MAUI Range Track](images/circularslider-range-track.png)

## See Also

- [Backtrack]({% slug circularslider-backtrack%})
- [Thumb Styling]({% slug circularslider-thumb-styling%})
- [Track Styling]({% slug circularslider-track-styling %})
