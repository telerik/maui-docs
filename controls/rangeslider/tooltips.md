---
title: Tooltips
page_title: .NET MAUI RangeSlider Documentation - Tooltips
description: Learn how to use the tooltips that Telerik UI RangeSlider for .NET MAUI control provides.
position: 7
slug: rangeslider-tooltips
---

# Tooltips

RangeSlider for .NET MAUI can display a tooltip to indicate the currently selected range to the end-user. The toolip is shown as soon as the user starts dragging the start thumb, the range track or the end thumb.

Check below the customization options for the RangeSlider tooltip:

* `TooltipStringFormat(string)`&mdash;Defines a custom string format that is used for displaying the content of the tooltip.
* `TooltipTemplate(DataTemplate)`&mdash;Sets a template or template selector that defines the content of the tooltip.
* `TooltipControlTemplate(ControlTemplate)`&mdash;Sets the control template of the tooltip that defines its overall appearance.

Check below a quick example with setting `TooltipStringFormat` and `TooltipTemplate` properties:

**1.** Add the custom `DataTemplate` to your page resources:

<snippet id='rangeslider-tooltiptemplate-datatemplate' />

**2.** Define the RangeSlider:

<snippet id='rangeslider-tooltiptemplate-xaml' />

## See Also

- [Range Thumb]({% slug rangeslider-range-thumb%})