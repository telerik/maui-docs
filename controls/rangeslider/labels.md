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

In order to display labels you need to define `LabelStep` and `LabelPlacement` properties of the RangeSlider.

* `LabelStep(double)`&mdash;Defines at what positions/values labels will be displayed.
* `LabelsPlacement(type Telerik.Maui.Controls.RangeSlider.SliderLabelsPlacement)`&mdash;Specifies the position of the labels in the RangeSlider with respect to its track. Available options are:
    * `None`&mdash;no labels are displayed;
    * `Start`&mdash;labels appear above the track.
    * `End`&mdash;labels appear below the track.

## Labels Formatting

Through the formatting properties you can easily modify only the labels text by applying a custom format. 

* `StringFormat(string)`&mdash;Defines a custom string format for the labels and the tooltips of the RangeSlider;
* `StringConverter(Telerik.Maui.IStringConverter)`&mdash;Specifies a custom string converter that can be used to define the content of a label or a tooltip for a given range slider value.

Here is a quick example with a custom string converter:

Add the following sample DictionaryStringConverter to your resources - in short, it replaces the values of the range with meaningful names in order to make the range more readable:

<snippet id='rangeslider-labels-stringconverter-dictionary' />

Define the RangeSlider with the converter applied:

<snippet id='rangeslider-labels-stringconverter' />

## LabelTemplate

You can customize what the RangeSlider labels render through the `LabelTemplate` property.

* `LabelTemplate (DataTemplate)`&mdash;Defines the template of the RangeSlider labels.

Check below a sample `LabelTemplate` example:

First define the custom DataTemplate:

<snippet id='rangeslider-labels-labeltemplate' />

Then apply it to the RangeSlider's `LabelTemplate`:

<snippet id='rangeslider-labels-labeltemplate-xaml' />

## See Also

- [Visual Structure]({% slug rangeslider-visual-structure%})
- [Ticks]({% slug rangeslider-ticks%})
- [Labels Styling]({% slug rangeslider-labels-styling%})