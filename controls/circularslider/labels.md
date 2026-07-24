---
title: Labels
page_title: .NET MAUI CircularSlider Documentation - Labels
description: Learn how to configure the labels of the Telerik UI CircularSlider for .NET MAUI. Set how labels display along the arc, or show custom text instead of range values.
position: 9
slug: circularslider-labels
---

# .NET MAUI CircularSlider Labels

The CircularSlider for .NET MAUI can show labels along the backtrack. This helps users to better understand the underlying range of values.

## Labels Step and Placement

To display labels, define the `LabelStep` and `LabelsPlacement` properties of the CircularSlider.

* `LabelStep` (`double`)&mdash;Defines the values on the backtrack that are indicated by labels. Each label is placed at the specified value interval. For example, if `LabelStep="5"`, your labels show the 0, 5, 10, 15, and 20 values on a 0-20 backtrack.
* `LabelsPlacement` (`Telerik.Maui.Controls.RangeSlider.SliderLabelsPlacement`)&mdash;Defines where the labels are displayed relative to the position of the backtrack. The available options are:
    * `None`&mdash;No labels are displayed.
    * `Start`&mdash;The labels appear on the inner side of the arc.
    * `End`&mdash;The labels appear on the outer side of the arc.

Check an example on how you can configure labels:

<snippet id='circularslider-labels-settings' />

![Telerik CircularSlider for .NET MAUI Labels](images/circularslider-labels-settings.png)

## Full Circle Label Display Mode

When the CircularSlider forms a full circle, the first (minimum) and last (maximum) value labels overlap at the same position. Use the `FullCircleLabelDisplayMode` property to control which label is shown at that overlap point.

* `FullCircleLabelDisplayMode` (`Telerik.Maui.Controls.CircularSlider.CircularSliderFullCircleLabelDisplayMode`)&mdash;Defines which label is shown at the overlap point when the slider is a full circle. The available options are:
    * `ShowFirst`&mdash;The first (minimum) value label is shown at the overlap point. This is the default value.
    * `ShowLast`&mdash;The last (maximum) value label is shown at the overlap point.

<snippet id='circularslider-full-circle-label-display-mode' />

## Labels Formatting

You can use the formatting properties to modify the text of the labels.

* `StringFormat` (`string`)&mdash;Defines a custom string format for the labels of the CircularSlider.
* `StringConverter` (`Telerik.Maui.IStringConverter`)&mdash;Defines a custom string converter. You can use the string converter to replace the range values with more user-friendly names in your CircularSlider labels.

Here is a quick example with a custom string converter:

1. Add the following sample Dictionary String Converter to your resources. It replaces the values of the range with meaningful names to make the range more readable:

<snippet id='circularslider-labels-stringconverter-dictionary' />

2. Apply the converter to the CircularSlider:

<snippet id='circularslider-labels-stringconverter' />

3. Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

![Telerik CircularSlider for .NET MAUI Labels StringConverter](images/circularslider-labels-stringconverter.png)

## Label Template

You can use the `LabelTemplate` property to customize how the CircularSlider labels render.

* `LabelTemplate` (`DataTemplate`)&mdash;Defines the template of the CircularSlider labels.

Check below a sample `LabelTemplate` example:

1. Add the custom `DataTemplate` to your page resources:

<snippet id='circularslider-labels-labeltemplate' />

2. Apply it to the CircularSlider's `LabelTemplate`:

<snippet id='circularslider-labels-labeltemplate-xaml' />

![Telerik CircularSlider for .NET MAUI Label Template](images/circularslider-labels-template.png)

## See Also

- [Ticks]({% slug circularslider-ticks%})
- [Tooltips]({% slug circularslider-tooltips %})
- [Labels Styling]({% slug circularslider-labels-styling%})
