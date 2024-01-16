---
title: Ticks Styling
page_title: .NET MAUI Slider Documentation - Ticks Styling
description: Learn how to style the ticks of the Telerik UI for .NET MAUI Slider. Set the size and style ticks within and outside of the range track differently.
position: 2
slug: slider-ticks-styling
---

# Ticks Styling

The Slider for .NET MAUI control provides styling properties for its ticks as well as a style selector, which you can use to apply different styles to the ticks according to custom logic.

 * `InRangeTickColor`(`Color`)&mdash;Defines the color of the ticks that correspond to the range track (between `OriginValue` and `Value`).
 * `OutOfRangeTickColor`(`Color`)&mdash;Specifies the color of the ticks that are outside of the range defined by the slider's range track.
 * `TickThickness`(`double`)&mdash;Defines the width of the ticks.
 * `InRangeTickStyle`(`Style`)&mdash;Specifies custom style to the ticks that correspond to the range track (between `OriginValue` and `Value`).
 * `OutOfRangeTickStyle`(`Style`)&mdash;Specifies custom style to the ticks that are outside of the range defined by the slider's range track.
 * `TickLength`(`double`)&mdash;Specified custom length to the ticks.
 * `TicksStyleSelector`(`Telerik.Maui.Controls.IStyleSelector`)&mdash;Defines a selector that can apply different styles to ticks according to custom logic.

## Tick Styles Example

Check below an example on how you can utilize the tick style properties.

**1.** Add Styles with TargetType set to `RadBorder` to the page's resources:

<snippet id='slider-ticksttyling-styles' />

**2.** Add the Slider definition with the Style properties applied:

<snippet id='slider-ticksttyling-xaml' />

![Telerik Slider for .NET MAUI Ticks Styling](images/slider-ticks-styling.png)

## Tick Style Selector Example

Here is a quick example on how the `TicksStyleSelector` can be applied to set separate styles to the major/minor ticks.

**1.** Create a custom style selector class which inherits from `Telerik.Maui.Controls.IStyleSelector`:

<snippet id='slider-ticks-styleselector-class' />

>`Telerik.Maui.Controls.IStyleSelector` provides a mechanism to select a `Microsoft.Maui.Controls.Style` based on a custom logic.

**2.** Add The style selector to the page's resources:

<snippet id='slider-tickstyleselector-selector'/>

**3.** Define the Slider with the style selector applied:

<snippet id='slider-tickstyleselector-xaml'/>

Check the result below:

![Telerik Slider for .NET MAUI Ticks Styling](images/slider-ticks-styleselector.png)

## See Also

- [Ticks]({% slug slider-ticks%})
- [Range Track]({%slug slider-range-track%})
- [Track Styling]({% slug slider-track-styling%})
- [Labels Styling]({% slug slider-labels-styling%})