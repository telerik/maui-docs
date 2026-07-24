---
title: Ticks Styling
page_title: .NET MAUI CircularSlider Documentation - Ticks Styling
description: Learn how to style the ticks of the Telerik UI for .NET MAUI CircularSlider. Set the size and style ticks within and outside of the range track differently.
position: 2
slug: circularslider-ticks-styling
---

# .NET MAUI CircularSlider Ticks Styling

The CircularSlider for .NET MAUI provides the following styling options and a style selector for the ticks (to let you apply additional styles):

 * `InRangeTickColor` (`Color`)&mdash;Defines the color of the ticks shown along the range track (between `OriginValue` and `Value`).
 * `OutOfRangeTickColor` (`Color`)&mdash;Defines the color of the ticks shown outside of the range track.
 * `TickThickness` (`double`)&mdash;Defines the width of the ticks.
 * `TickLength` (`double`)&mdash;Defines the custom length of the ticks.
 * `InRangeTickStyle` (`Style`)&mdash;Defines a custom style for the ticks shown along the range track.
 * `OutOfRangeTickStyle` (`Style`)&mdash;Defines a custom style for the ticks shown outside of the range track.
 * `TickStyleSelector` (`Telerik.Maui.Controls.IStyleSelector`)&mdash;Defines a selector that can apply different styles to ticks according to custom logic.

## Tick Styles Example

The following example demonstrates how to use the described styling properties to style the CircularSlider's ticks:

1. Add the custom styles to the page's resources:

<snippet id='circularslider-ticks-styling-styles' />

2. Apply the custom styles to the CircularSlider:

<snippet id='circularslider-ticks-styling-xaml' />

![Telerik CircularSlider for .NET MAUI Ticks Styling](images/circularslider-ticks-styling.png)

## TickStyleSelector Example

The following example demonstrates how to use the `TickStyleSelector` to set two different styles for the major and minor ticks:

1. Add the style selector to the page's resources:

<snippet id='circularslider-tickstyleselector-selector'/>

2. Apply the style selector to the CircularSlider:

<snippet id='circularslider-tickstyleselector-xaml'/>

> `Telerik.Maui.Controls.IStyleSelector` provides a mechanism to select a `Microsoft.Maui.Controls.Style` based on custom logic.

![Telerik CircularSlider for .NET MAUI Ticks Style Selector](images/circularslider-ticks-styleselector.png)

## See Also

- [Ticks]({% slug circularslider-ticks%})
- [Range Track]({%slug circularslider-range-track%})
- [Track Styling]({% slug circularslider-track-styling%})
- [Labels Styling]({% slug circularslider-labels-styling%})
