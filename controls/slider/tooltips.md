---
title: Tooltips
page_title: .NET MAUI Slider Documentation - Tooltips
description: Learn how to use the tooltips that Telerik UI Slider for .NET MAUI control provides.
position: 7
slug: slider-tooltips
---

# Tooltips

Slider for .NET MAUI can display a tooltip to indicate the currently selected value to the end-user. The toolip is shown as soon as the user starts dragging the thumb.

Check below the customization options for the Slider tooltip:

* `TooltipStringFormat`(`string`)&mdash;Defines a custom string format that is used for displaying the content of the tooltip.
* `TooltipTemplate`(`DataTemplate`)&mdash;Sets a template or template selector that defines the content of the tooltip.
* `TooltipControlTemplate`(`ControlTemplate`)&mdash;Sets the control template of the tooltip that defines its overall appearance.

## TooltipTemplate Example

Check below a quick example with setting `TooltipStringFormat` and `TooltipTemplate` properties:

**1.** Add the custom `DataTemplate` to your page resources:

<snippet id='slider-tooltiptemplate-datatemplate' />

**2.** Define the Slider control:

<snippet id='slider-tooltiptemplate-xaml' />

Check the Slider modified tooltip below:

![Telerik Slider for .NET MAUI Tooltip](images/slider-tooltips-template.png)

## TooltipControlTemplate Example

Here is quick example on how the Slider's Tooltip ControlTemplate can be customized:

**1.** Add the custom `ControlTemplate` to your page resources:

<snippet id='slider-tooltiptemplate-controltemplate' />

**2.** Define the Slider control:

<snippet id='slider-tooltipcontroltemplate-xaml' />

Check the Slider modified tooltip below:

![Telerik Slider for .NET MAUI Tooltip](images/slider-tooltips-controltemplate.png)

## See Also

- [Value Thumb]({% slug slider-value-thumb%})