---
title: Tooltips
page_title: .NET MAUI Slider Documentation - Tooltips
description: Learn how to use the tooltips that the Telerik UI Slider for .NET MAUI control provides.
position: 9
slug: slider-tooltips
---

# .NET MAUI Slider Tooltips

The Slider for .NET MAUI can display a tooltip to indicate the currently selected value to the end user. The tooltip displays as soon as the user starts dragging the thumb.

The Slider tooltip provides the following customization options:

* `TooltipStringFormat`(`string`)&mdash;Defines a custom string format for the tooltip.
* `TooltipContentTemplate`(`DataTemplate`)&mdash;Sets a template or template selector that defines the content of the tooltip.
* `TooltipControlTemplate`(`ControlTemplate`)&mdash;Sets the control template of the tooltip that defines its overall appearance.

## TooltipContentTemplate Example

Check below a quick example with setting the `TooltipStringFormat` and `TooltipContentTemplate` properties:

**1.** Add the custom `DataTemplate` to your page resources:

<snippet id='slider-tooltiptemplate-datatemplate' />

**2.** Apply it to the Slider's `TooltipContentTemplate`:

<snippet id='slider-tooltiptemplate-xaml' />

Check the result below:

![Telerik Slider for .NET MAUI Tooltip](images/slider-tooltips-template.png)

## TooltipControlTemplate Example

Check below a quick example with setting the `TooltipControlTemplate` property:

**1.** Add the custom `ControlTemplate` to your page resources:

<snippet id='slider-tooltiptemplate-controltemplate' />

**2.** Apply it to the Slider's `TooltipControlTemplate`:

<snippet id='slider-tooltipcontroltemplate-xaml' />

Check the result below:

![Telerik Slider for .NET MAUI Tooltip](images/slider-tooltips-controltemplate.png)

## See Also

- [Value Thumb]({% slug slider-value-thumb%})
