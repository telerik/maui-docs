---
title: Animations
page_title: .NET MAUI Gauge Documentation | Animations
description: "Control the animations behavior of the Telerik Gauge for .NET MAUI by using the supported animation options."
position: 3
previous_url: /controls/gauge/gauge-animations
slug: gauge-animations
---

# Animations

All Gauge indicators are animated upon initial load and upon value change. The animations are enabled by default.

To control the Gauge animations, use the `AnimationSettings` property by applying it either to the Gauge or separately to its indicators. By default, the property of the indicator is `null` and in this case the `AnimationSettings` property of the Gauge will be considered. This behavior allows you to control all animations by setting a single property, that of the Gauge. To animate an indicator differently, set its `AnimationSettings` property as it has a higher precedence than the Gauge property.

The `AnimationSettings` class contains the following properties:

* Duration (`int`)&mdash;Defines the duration of the animation in milliseconds.
* Easing&mdash;Defines the easing of the animation.
* Enabled (`bool`)&mdash;Specifies whether the animation will be enabled or not. By default, the `Enabled` property is `true`.

The following example demonstrates how to set the `AnimationSettings` property:

```XAML
<telerikGauges:RadRadialGauge x:Name="gauge1"
                              Grid.Row="1"
                              Grid.Column="1">
    <telerikGauges:RadRadialGauge.AnimationSettings>
        <telerikCommon:AnimationSettings x:Name="gauge1Animations" Easing="CubicOut" />
    </telerikGauges:RadRadialGauge.AnimationSettings>
    <telerikGauges:RadRadialGauge.Axis>
        <telerikGauges:GaugeLinearAxis Maximum="200"
                                       Minimum="0"
                                       Step="25" />
    </telerikGauges:RadRadialGauge.Axis>
    <telerikGauges:RadRadialGauge.Indicators>
        <telerikGauges:GaugeShapeIndicator Value="80" />
        <telerikGauges:GaugeBarIndicator Offset="30" Value="100" />
        <telerikGauges:GaugeNeedleIndicator Fill="Blue"
                                            Offset="30"
                                            Value="120" />
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

The following GIF animation shows all animations supported by the Gauge.

![Gauge Animations](images/gauge-animations.gif)

## See Also

- [Indicators]({%slug gauge-indicators%})
- [Positioning]({%slug gauge-positioning%})
- [Ranges]({%slug gauge-ranges%})
