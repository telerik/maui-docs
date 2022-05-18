---
title: Radial Gauge
page_title: .NET MAUI Gauge Documentation | Radial Gauge
description: "Get started with the Telerik UI for .NET MAUI Radial Gauge and add the control to your .NET MAUI project."
position: 0
previous_url: /controls/gauge/gauge-types/gauge-types-radial
slug: gauge-types-radial
---

# Radial Gauge

The Radial Gauge allows you to display the scale range in a radial form.

## Setting Up the Radial Gauge

The following example shows the basic setup of the Radial Gauge.

<snippet id='gauge-types-radialgauge-xaml'/>

The following image shows the end result.

![Radial gauge example](../images/gauge-types-radial-gauge-0.png)

## Setting the Rotation and Radius

The Radial Gauge allows you to define the radius of its axis through its **AxisRadiusFactor** property. For more information about the **AxisRadiusFactor**, refer to the article on [positioning and offset]({%slug gauge-positioning%}#radial-gauge-specifics).

You can also control the start angle, the sweep angle, and the sweep direction of the axis through the following properties:

- **StartAngle**&mdash;The start angle determines the origin position of the axis.
- **SweepAngle**&mdash;The sweep angle defines the size of the axis arc. For example, if the start angle is 90 and the sweep angle is 30, the axis will be drawn between the 90<sup>th</sup> and 120<sup>th</sup> angle. If the sweep direction is counter-clockwise, the axis will be drawn between 60 and 90.
- **SweepDirection**&mdash;Sets the axis sweep direction as clockwise or counter-clockwise.

## See Also

- [Horizontal Gauge]({%slug gauge-types-horizontal%})
- [Vertical Gauge]({%slug gauge-types-vertical%})
- [Axis]({%slug gauge-axis%})
- [Indicators]({%slug gauge-indicators%})
- [Ranges]({%slug gauge-ranges%})
