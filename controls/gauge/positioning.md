---
title: Positioning and Offset
page_title: .NET MAUI Gauge Documentation - Positioning and Offset
description: Learn how to set the position and offset of the indicators when working with the Telerik Gauge for .NET MAUI control and learn what the Radial Gauge specifics are.
position: 5
previous_url: /controls/gauge/gauge-positioning
slug: gauge-positioning
---

# .NET MAUI Gauge Positioning and Offset

The gauge arranges most of its elements by taking into consideration the respective position and offset properties.

Some elements like the indicators have properties named `Position` and `Offset`. Other elements are composite, like the axis that handles both ticks and labels, and requires two sets of properties - `TickPosition` and `TickOffset`, and `LabelPosition` and `LabelOffset`.

The offset is the distance from the axis line to the element. The gauge allows the overlapping of elements and you have to set adequate offset values to ensure that they are not positioned on top of each other.

In the example below, all elements are arranged so that they are 2 pixels apart and never overlap each other.

```XAML
<telerik:RadRadialGauge x:Name="gauge"
						  Margin="2"
						  AxisRadiusFactor="1"
						  StartAngle="90"
						  SweepAngle="360">
    <telerik:RadRadialGauge.Axis>
        <telerik:GaugeLinearAxis Maximum="100"
                                       Minimum="0"
                                       ShowLabels="False"
                                       StrokeThickness="0" />
    </telerik:RadRadialGauge.Axis>
    <telerik:RadRadialGauge.Ranges>
        <telerik:GaugeRangesDefinition EndThickness="1"
                                             StartThickness="1"
                                             Offset="0">
            <telerik:GaugeRange Color="#FFDD789B"
                                      From="0"
                                      To="25" />
            <telerik:GaugeRange Color="#FFAAC271"
                                      From="25"
                                      To="50" />
            <telerik:GaugeRange Color="#FF4062AD"
                                      From="50"
                                      To="75" />
        </telerik:GaugeRangesDefinition>
    </telerik:RadRadialGauge.Ranges>
    <telerik:RadRadialGauge.Indicators>
        <telerik:GaugeBarIndicator EndCap="Oval"
                                         EndThickness="10"
                                         Fill="#FFDD789B"
                                         StartThickness="10"
                                         Offset="3"
                                         Value="12.5" />
        <telerik:GaugeBarIndicator EndCap="Oval"
                                         EndThickness="10"
                                         Fill="#FFAAC271"
                                         StartThickness="10"
                                         Offset="15"
                                         Value="37.5" />
        <telerik:GaugeBarIndicator EndCap="Oval"
                                         EndThickness="10"
                                         Fill="#FF4062AD"
                                         StartThickness="10"
                                         Offset="27"
                                         Value="62.5" />
        <telerik:GaugeShapeIndicator Fill="#FF4062AD"
                                           Position="Start"
                                           Offset="39"
                                           Value="56" />
        <telerik:GaugeNeedleIndicator Fill="#FFAAC271"
                                            Offset="51"
                                            Value="37.5" />
    </telerik:RadRadialGauge.Indicators>
</telerik:RadRadialGauge>
```

The following image shows the end result.

![Gauge position and offset](images/gauge-positioning.png)

## Radial Gauge Specifics

While the offset is the absolute distance from the axis line to the element, the position of the axis line itself is determined by the `AxisRadiusFactor` property, which is a relative value between 0 and 1.

When the Radial Gauge is arranged, it calculates the largest square box in the middle of its arrange bounds and the gauge is laid out within this square box. The `AxisRadiusFactor` determines the size of the radius of the axis arc inside this box. Setting the radius factor to 1.0 results in the axis line occupying the space that is possible.

## See Also

- [Indicators]({%slug gauge-indicators%})
- [Ranges]({%slug gauge-ranges%})
