---
title: Labels
page_title: .NET MAUI Slider Documentation - Labels
description: Learn how to configure the labels of the Telerik UI Slider for .NET MAUI. Set how labels display on the backtrack, or show custom text instead of range values.
position: 8
slug: slider-labels
---

# .NET MAUI Slider Labels

The Slider for .NET MAUI can show labels along the backtrack. This helps users to better understand the underlying range of values.

## Labels Step and Placement

To display labels, define the `LabelStep` and `LabelPlacement` properties of the Slider.

* `LabelStep`(`double`)&mdash;Defines the values on the backtrack that will be indicated by labels. Each label will be placed at the specified value interval. For example, if `LabelStep="5"`, your labels will show the 0, 5, 10, 15, and 20 values on a 0-20 backtrack.
* `LabelsPlacement`(`Telerik.Maui.Controls.RangeSlider.SliderLabelsPlacement`)&mdash;Defines where the labels are displayed relative to the position of the backtrack. The available options are:
    * `None`&mdash;No labels are displayed.
    * `Start`&mdash;The labels appear above the backtrack.
    * `End`&mdash;The labels appear below the backtrack.

Check an example on how you can configure labels:

<snippet id='slider-labels-settings' />

![Telerik Slider for .NET MAUI Labels](images/slider-labels-settings.png)

## Labels Formatting

You can use the formatting properties to modify the text of the labels. 

* `StringFormat`(`string`)&mdash;Defines a custom string format for the labels of the Slider.
* `StringConverter`(`Telerik.Maui.IStringConverter`)&mdash;Defines a custom string converter. You can use the string converter to replace the range values with more user-friendly names in your Slider labels.  

Here is a quick example with a custom string converter:

**1.** Add the following sample Dictionary String Converter to your resources. It replaces the values of the range with meaningful names to make the range more readable:

<snippet id='slider-labels-stringconverter-dictionary' />

**2.** Apply the converter to the Slider:

<snippet id='slider-labels-stringconverter' />

Check the result below:

![Telerik Slider for .NET MAUI Labels StringConverter](images/slider-labels-stringconverter.png)

## Label Template

You can use the `LabelTemplate` property to customize how the Slider labels render.

* `LabelTemplate`(`DataTemplate`)&mdash;Defines the template of the Slider labels.

Check below a sample `LabelTemplate` example:

**1.** Add the custom `DataTemplate` to your page resources:

<snippet id='slider-labels-labeltemplate' />

**2.** Apply it to the Slider's `LabelTemplate`:

<snippet id='slider-labels-labeltemplate-xaml' />

Check the result below:

![Telerik Slider for .NET MAUI Label Template](images/slider-labels-template.png)

## See Also

- [Ticks]({% slug slider-ticks%})
- [Tooltips]({% slug slider-tooltips %})
- [Labels Styling]({% slug slider-labels-styling%})
