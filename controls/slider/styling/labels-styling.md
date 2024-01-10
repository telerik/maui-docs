---
title: Labels Styling
page_title: .NET MAUI Slider Documentation - Labels Styling
description: Review the styling options that the Telerik UI for .NET MAUI Slider control provides for its labels.
position: 3
slug: slider-labels-styling
---

# Labels Styling

The Slider for .NET MAUI control provides styling properties for its labels as well as a style selector, which you can use to apply different styles to the labels according to custom logic.

* `TextColor`&mdash;Defines a custom color for the labels.
* `FontFamily`&mdash;Specifies custom font family to the labels.
* `FontSize`&mdash;Specifies custom font size to the labels.
* `LabelStyle`&mdash;Defines custom style to the labels.

* `LabelStyleSelector`(`Telerik.Maui.Controls.IStyleSelector`)&mdash;Defines a selector that can apply different styles to different labels.

Here is a quick example on how the `LabelStyleSelector` can be applied to set separate styles to the labels according to the `Value` and `OriginValue` properties:

**1.** Create a custom style selector class which inherits from `Telerik.Maui.Controls.IStyleSelector` - the style selector sets `InsideRangeStyle` to the labels that correspond to the slider's range track (between `OriginValue` and `Value`) and `OutsideRangeStyle` to all the other labels.

<snippet id='slider-labels-styleselector-class' />

>`Telerik.Maui.Controls.IStyleSelector` provides a mechanism to select a `Microsoft.Maui.Controls.Style` based on a custom logic.

**2.** Add The style selector to the page's resources:

<snippet id='slider-styling-labelsstyleselector'/>

**3.** Define the Slider with the style selector applied:

<snippet id='slider-styling-labelsstyleselector-xaml'/>

Check the result below:

![Telerik Slider for .NET MAUI Labels Styling](images/slider-labels-styling.png)

## See Also

- [Labels]({% slug slider-labels%})
- [Range Track]({%slug slider-range-track%})
- [Track Styling]({% slug slider-track-styling%})
- [Ticks Styling]({% slug slider-ticks-styling%})