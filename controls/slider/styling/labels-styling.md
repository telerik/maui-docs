---
title: Labels Styling
page_title: .NET MAUI Slider Documentation - Labels Styling
description: Learn how to style the labels of the Telerik UI for .NET MAUI Slider. Set the colors and fonts, or use the style selector for a more complex styling approach.
position: 3
slug: slider-labels-styling
---

# .NET MAUI Slider Labels Styling

The Slider for .NET MAUI provides the following styling options and a style selector for the labels (to let you apply additional styles):

* `TextColor`&mdash;Defines a custom color for the labels.
* `FontFamily`&mdash;Defines a custom font family for the labels.
* `FontSize`&mdash;Defines a custom font size for the labels.
* `LabelStyle`&mdash;Defines a custom style for the labels.

* `LabelStyleSelector`(`Telerik.Maui.Controls.IStyleSelector`)&mdash;Defines a selector that can apply different styles to different labels according to custom logic.

The following example demonstrates how to use the `LabelStyleSelector` to apply different styles to the labels based on the `Value` and `OriginValue` properties:

**1.** Create a custom style selector class which inherits from `Telerik.Maui.Controls.IStyleSelector`. The style selector sets `InsideRangeStyle` to the labels that correspond to the slider's range track (between `OriginValue` and `Value`) and `OutsideRangeStyle` to all the other labels.

<snippet id='slider-labels-styleselector-class' />

>`Telerik.Maui.Controls.IStyleSelector` provides a mechanism to select a `Microsoft.Maui.Controls.Style` based on custom logic.

**2.** Add the style selector to the page's resources:

<snippet id='slider-styling-labelsstyleselector'/>

**3.** Apply the style selector to the Slider:

<snippet id='slider-styling-labelsstyleselector-xaml'/>

Check the result below:

![Telerik Slider for .NET MAUI Labels Styling](images/slider-labels-styling.png)

## See Also

- [Labels]({% slug slider-labels%})
- [Range Track]({%slug slider-range-track%})
- [Track Styling]({% slug slider-track-styling%})
- [Ticks Styling]({% slug slider-ticks-styling%})