---
title: Horizontal Gauge
page_title: .NET MAUI Gauge Documentation | Horizontal Gauge
description: "Get started with the Telerik UI for .NET MAUI Horizontal Gauge and add the control to your .NET MAUI project."
position: 1
slug: gauge-types-horizontal
---

# Horizontal Gauge

The Horizontal Gauge allows you to display the scale range in a linear form and horizontally oriented.

The following example shows the basic setup of the Horizontal Gauge.

```XAML
<telerikGauges:RadHorizontalGauge x:Name="gauge">
    <telerikGauges:RadHorizontalGauge.Axis>
        <telerikGauges:GaugeLinearAxis Maximum="200"
                                       Minimum="0"
                                       Step="25" />
    </telerikGauges:RadHorizontalGauge.Axis>
    <telerikGauges:RadHorizontalGauge.Indicators>
        <telerikGauges:GaugeShapeIndicator Value="90" />
    </telerikGauges:RadHorizontalGauge.Indicators>
    <telerikGauges:RadHorizontalGauge.Ranges>
        <telerikGauges:GaugeRangesDefinition>
            <telerikGauges:GaugeRange Color="Green"
                                      From="0"
                                      To="150" />
            <telerikGauges:GaugeGradientRange From="150" To="200">
                <telerikCommon:RadGradientStop Offset="150" Color="Yellow" />
                <telerikCommon:RadGradientStop Offset="200" Color="Red" />
            </telerikGauges:GaugeGradientRange>
        </telerikGauges:GaugeRangesDefinition>
    </telerikGauges:RadHorizontalGauge.Ranges>
</telerikGauges:RadHorizontalGauge>
```

The following image shows the end result.

![Radial gauge example](../images/gauge-types-horizontal-gauge-0.png)

## See Also

- [Radial Gauge]({%slug gauge-types-radial%})
- [Vertical Gauge]({%slug gauge-types-vertical%})
- [Axis]({%slug gauge-axis%})
- [Indicators]({%slug gauge-indicators%})
- [Ranges]({%slug gauge-ranges%})
