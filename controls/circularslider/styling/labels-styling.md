---
title: Labels Styling
page_title: .NET MAUI CircularSlider Documentation - Labels Styling
description: Learn how to style the labels of the Telerik UI for .NET MAUI CircularSlider. Set the colors and fonts, or use the style selector for a more complex styling approach.
position: 3
slug: circularslider-labels-styling
---

# .NET MAUI CircularSlider Labels Styling

The CircularSlider for .NET MAUI provides the following styling options and a style selector for the labels (to let you apply additional styles):

* `TextColor` (`Color`)&mdash;Defines a custom color for the labels.
* `FontFamily` (`string`)&mdash;Defines a custom font family for the labels.
* `FontSize` (`double`)&mdash;Defines a custom font size for the labels.
* `LabelStyle` (`Style`)&mdash;Defines a custom style for the labels.
* `LabelStyleSelector` (`Telerik.Maui.Controls.IStyleSelector`)&mdash;Defines a selector that can apply different styles to different labels according to custom logic.

The following example demonstrates how to use the `LabelStyleSelector` to apply different styles to the labels based on the `Value` and `OriginValue` properties:

1. Add the style selector to the page's resources:

<snippet id='circularslider-labelsstyleselector-selector'/>

2. Apply the style selector to the CircularSlider:

<snippet id='circularslider-labelsstyleselector-xaml'/>

> `Telerik.Maui.Controls.IStyleSelector` provides a mechanism to select a `Microsoft.Maui.Controls.Style` based on custom logic.

![Telerik CircularSlider for .NET MAUI Labels Styling](images/circularslider-labels-styling.png)

## See Also

- [Labels]({% slug circularslider-labels%})
- [Range Track]({%slug circularslider-range-track%})
- [Track Styling]({% slug circularslider-track-styling%})
- [Ticks Styling]({% slug circularslider-ticks-styling%})
