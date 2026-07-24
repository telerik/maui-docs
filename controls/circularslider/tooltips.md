---
title: Tooltips
page_title: .NET MAUI CircularSlider Documentation - Tooltips
description: Learn how to use the tooltips that the Telerik UI CircularSlider for .NET MAUI control provides.
position: 10
slug: circularslider-tooltips
---

# .NET MAUI CircularSlider Tooltips

The CircularSlider for .NET MAUI can display a tooltip to indicate the currently selected value to the end user. The tooltip displays as soon as the user starts dragging the thumb.

The CircularSlider tooltip provides the following customization options:

* `TooltipStringFormat` (`string`)&mdash;Defines a custom string format for the tooltip.
* `TooltipContentTemplate` (`DataTemplate`)&mdash;Defines a template or template selector that defines the content of the tooltip.
* `TooltipControlTemplate` (`ControlTemplate`)&mdash;Defines the control template of the tooltip that defines its overall appearance.

## TooltipContentTemplate Example

Check below a quick example with setting the `TooltipStringFormat` and `TooltipContentTemplate` properties:

1. Add the custom `DataTemplate` to your page resources:

<snippet id='circularslider-tooltip-content-template' />

2. Apply it to the CircularSlider's `TooltipContentTemplate`:

<snippet id='circularslider-tooltiptemplate-controltemplate' />

3. Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

![Telerik CircularSlider for .NET MAUI Tooltip](images/circularslider-tooltips-template.png)

## TooltipControlTemplate Example

Here is a quick example with setting the `TooltipControlTemplate` property:

<snippet id='circularslider-tooltipcontroltemplate-xaml' />

![Telerik CircularSlider for .NET MAUI Tooltip](images/circularslider-tooltips-controltemplate.png)

## See Also

- [Value Thumb]({% slug circularslider-value-thumb%})
- [Labels]({% slug circularslider-labels%})
