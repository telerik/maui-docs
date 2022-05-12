---
title: Vertical Gauge
page_title: .NET MAUI Gauge Documentation | Vertical Gauge
description: "Get started with the Telerik UI for .NET MAUI Vertical Gauge and add the control to your .NET MAUI project."
position: 2
previous_url: /controls/gauge/gauge-types/gauge-types-vertical
slug: gauge-types-vertical
---

# Vertical Gauge

The Vertical Gauge allows you to display the scale range in a linear form and vertically oriented.

The following example shows the basic setup of the Vertical Gauge.

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


The following image shows the end result.

![Vertical gauge example](../images/gauge-types-vertical-gauge-0.png)

## See Also

- [Radial Gauge]({%slug gauge-types-radial%})
- [Horizontal Gauge]({%slug gauge-types-horizontal%})
- [Axis]({%slug gauge-axis%})
- [Indicators]({%slug gauge-indicators%})
- [Ranges]({%slug gauge-ranges%})
