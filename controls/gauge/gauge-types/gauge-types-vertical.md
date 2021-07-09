---
title: Vertical Gauge
page_title: .NET MAUI Gauge Documentation | Vertical Gauge
description: Check our &quot;Vertical Gauge&quot; documentation article for Telerik Gauge for .NET MAUI control.
position: 2
slug: gauge-types-vertical
---

# Vertical Gauge

The **RadVerticalGauge** control allows you to display the scale's range in a linear form, vertically oriented.

## Setting up the gauge

The following example shows a **RadVerticalGauge**'s basic set up.

```XAML
<telerikGauges:RadVerticalGauge x:Name="gauge">
    <telerikGauges:RadVerticalGauge.Axis>
        <telerikGauges:GaugeLinearAxis Maximum="200"
                                       Minimum="0"
                                       Step="25" />
    </telerikGauges:RadVerticalGauge.Axis>
    <telerikGauges:RadVerticalGauge.Indicators>
        <telerikGauges:GaugeShapeIndicator Value="90" />
    </telerikGauges:RadVerticalGauge.Indicators>
    <telerikGauges:RadVerticalGauge.Ranges>
        <telerikGauges:GaugeRangesDefinition>
            <telerikGauges:GaugeRange Color="Green"
                                      From="0"
                                      To="150" />
            <telerikGauges:GaugeGradientRange From="150" To="200">
                <telerikCommon:RadGradientStop Offset="150" Color="Yellow" />
                <telerikCommon:RadGradientStop Offset="200" Color="Red" />
            </telerikGauges:GaugeGradientRange>
        </telerikGauges:GaugeRangesDefinition>
    </telerikGauges:RadVerticalGauge.Ranges>
</telerikGauges:RadVerticalGauge>
```

Here is the result:

![Vertical gauge example](../images/gauge-types-vertical-gauge-0.png) 

## See Also
- [Radial Gauge]({%slug gauge-types-radial%})
- [Horizontal Gauge]({%slug gauge-types-horizontal%})
- [Axis]({%slug gauge-axis%})
- [Indicators]({%slug gauge-indicators%})
- [Ranges]({%slug gauge-ranges%})