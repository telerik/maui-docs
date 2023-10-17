---
title: Labels
page_title: .NET MAUI RangeSlider Documentation - Labels
description: Learn how to use the labels that Telerik UI RangeSlider for .NET MAUI control provides.
position: 7
slug: rangeslider-labels
---

# Labels

The RangeSlider for .NET MAUI can show labels along the track for clarity of what the underlying min-max range is.

## Labels Step and Placement

To display labels, define the `LabelStep` and `LabelPlacement` properties of the RangeSlider.

* `LabelStep(double)`&mdash;Defines at what positions/values labels will be displayed.
* `LabelsPlacement(type Telerik.Maui.Controls.RangeSlider.SliderLabelsPlacement)`&mdash;Specifies the position of the labels in the RangeSlider with respect to its track. The available options are:
    * `None`&mdash;no labels are displayed.
    * `Start`&mdash;labels appear above the track.
    * `End`&mdash;labels appear below the track.

Check an example on how labels can be configured:

<snippet id='rangeslider-labels-settings' />

![Telerik RangeSlider for .NET MAUI Labels](images/rangeslider-labels-settings.png)

## Labels Formatting

Through the formatting properties you can easily modify only the labels text by applying a custom format. 

* `StringFormat(string)`&mdash;Defines a custom string format for the labels and the tooltips of the RangeSlider.
* `StringConverter(Telerik.Maui.IStringConverter)`&mdash;Specifies a custom string converter that can be used to define the content of a label or a tooltip for a given range slider value.

Here is a quick example with a custom string converter:

**1.** Add the following sample Dictionary String Converter to your resources&mdash;in short, it replaces the values of the range with meaningful names in order to make the range more readable:

<snippet id='rangeslider-labels-stringconverter-dictionary' />

**2.** Define the RangeSlider with the converter applied:

<snippet id='rangeslider-labels-stringconverter' />

Check the result below:

![Telerik RangeSlider for .NET MAUI Labels StringConverter](images/rangeslider-labels-stringconverter.png)

## Label Template

You can customize what the RangeSlider labels render through the `LabelTemplate` property.

* `LabelTemplate (DataTemplate)`&mdash;Defines the template of the RangeSlider labels.

Check below a sample `LabelTemplate` example:

**1.** First define the custom DataTemplate:

<snippet id='rangeslider-labels-labeltemplate' />

**2.** Apply it to the RangeSlider's `LabelTemplate`:

<snippet id='rangeslider-labels-labeltemplate-xaml' />

Here is the result:

![Telerik RangeSlider for .NET MAUI Label Template](images/rangeslider-labels-template.png)

## See Also

- [Ticks]({% slug rangeslider-ticks%})
- [Labels Styling]({% slug rangeslider-labels-styling%})