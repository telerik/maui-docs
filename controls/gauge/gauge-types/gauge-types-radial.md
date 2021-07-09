---
title: Radial Gauge
page_title: .NET MAUI Gauge Documentation | Radial Gauge
description: Check our &quot;Radial Gauge&quot; documentation article for Telerik Gauge for .NET MAUI control.
position: 0
slug: gauge-types-radial
---

# Radial Gauge

The **RadRadialGauge** control allows you to display the scale's range in a radial form.

## Setting up the gauge

The following example shows a **RadRadialGauge**'s basic set up.

```XAML
<telerikGauges:RadRadialGauge x:Name="gauge">
    <telerikGauges:RadRadialGauge.Axis>
        <telerikGauges:GaugeLinearAxis Maximum="200"
                                       Minimum="0"
                                       Step="25" />
    </telerikGauges:RadRadialGauge.Axis>
    <telerikGauges:RadRadialGauge.Indicators>
        <telerikGauges:GaugeNeedleIndicator Offset="30" Value="60" />
    </telerikGauges:RadRadialGauge.Indicators>
    <telerikGauges:RadRadialGauge.Ranges>
        <telerikGauges:GaugeRangesDefinition>
            <telerikGauges:GaugeRange Color="Green"
                                      From="0"
                                      To="150" />
            <telerikGauges:GaugeGradientRange From="150" To="200">
                <telerikCommon:RadGradientStop Offset="150" Color="Yellow" />
                <telerikCommon:RadGradientStop Offset="200" Color="Red" />
            </telerikGauges:GaugeGradientRange>
        </telerikGauges:GaugeRangesDefinition>
    </telerikGauges:RadRadialGauge.Ranges>
</telerikGauges:RadRadialGauge>
```

This is the result:

![Radial gauge example](../images/gauge-types-radial-gauge-0.png)

## Setting rotation and radius

The radial gauge allows you to define the radius of its axis. This can be done via the **AxisRadiusFactor** property of **RadRadialGauge**. Read more about the property in the [Positioning]({%slug gauge-positioning%}#radial-gauge-specifics) help article.

You can also control the start angle, the sweep angle and sweep direction of the axis. This can be done via the following properties:
- **StartAngle**: The start angle determines the origin position of the axis.
- **SweepAngle**: The sweep angle defines the size of the axis' arc. For example, if the start angle is 90 and the sweep angle is 30, the axis will be drawn between the 90th and 120th angle. If the sweep direction is counter-clockwise, the axis will be drawn between 60 and 90.
- **SweepDirection**: You can use this property to set the axis sweep direction - clockwise or counter-clockwise.

## See Also
- [Horizontal Gauge]({%slug gauge-types-horizontal%})
- [Vertical Gauge]({%slug gauge-types-vertical%})
- [Axis]({%slug gauge-axis%})
- [Indicators]({%slug gauge-indicators%})
- [Ranges]({%slug gauge-ranges%})