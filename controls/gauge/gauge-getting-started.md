---
title: Getting Started
page_title: .NET MAUI Gauge Documentation | Getting Started
description: "Get started with the Telerik UI for .NET MAUI Gauge and add the control to your .NET MAUI project."
position: 1
slug: gauge-getting-started
---

# Getting Started

This guide provides the information you need to start using the Telerik UI for .NET MAUI Gauge by adding the control to your project.

At the end, you will be able to achieve the following result.

![Gauge example](images/gauge-gettingstarted.png)

## Prerequisites

Before adding the Gauge, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

>important The Gauge is rendered through the [SkiaSharp graphics library](https://skia.org/).

## Define the Control

1. When the your .NET MAUI application is set up, you are ready to add a Gauge control to your page.

 ```XAML
<telerikGauges:RadRadialGauge x:Name="gauge">
    <telerikGauges:RadRadialGauge.Axis>
        <telerikGauges:GaugeLinearAxis Maximum="200"
                                       Minimum="0"
                                       Step="25" />
    </telerikGauges:RadRadialGauge.Axis>
    <telerikGauges:RadRadialGauge.Indicators>
        <telerikGauges:GaugeNeedleIndicator Offset="30" Value="60" />
        <telerikGauges:GaugeShapeIndicator Value="80" />
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

1. Add the following namespace:

 ```XAML
xmlns:telerikGauges="clr-namespace:Telerik.XamarinForms.DataVisualization.Gauges;assembly=Telerik.Maui.Controls.Compatibility"
xmlns:telerikCommon="clr-namespace:Telerik.XamarinForms.Common;assembly=Telerik.Maui.Controls.Compatibility"
 ```

1. Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `CreateMauiApp` method of the `MauiProgram.cs` file of your project:

 ```C#
 using Telerik.Maui.Controls.Compatibility;

 public static class MauiProgram
 {
	public static MauiApp CreateMauiApp()
	{
		var builder = MauiApp.CreateBuilder();
		builder
			.UseTelerik()
			.UseMauiApp<App>()
			.ConfigureFonts(fonts =>
			{
				fonts.AddFont("OpenSans-Regular.ttf", "OpenSansRegular");
			});

		return builder.Build();
	}
 }           
 ```

## See Also

- [Radial Gauge]({%slug gauge-types-radial%})
- [Horizontal Gauge]({%slug gauge-types-horizontal%})
- [Vertical Gauge]({%slug gauge-types-vertical%})
