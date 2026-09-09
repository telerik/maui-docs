---
title: Creating a Remaining Tasks Radial Gauge in .NET MAUI
description: Learn how to create a Remaining Tasks Radial Gauge using the Telerik UI for .NET MAUI Gauge component.
type: how-to
page_title: How to Create a Radial Gauge for Remaining Tasks in .NET MAUI
meta_title: How to Create a Radial Gauge for Remaining Tasks in .NET MAUI
slug: remaining-tasks-radial-gauge-dotnet-maui
tags: .net maui, gauge, radial gauge, gauge range, gauge indicator
res_type: kb
---

## Environment
<table>
<tbody>
<tr>
<td>Product</td>
<td>Gauge for UI for .NET MAUI</td>
</tr>
<tr>
<td>Version</td>
<td>15.0.0</td>
</tr>
</tbody>
</table>

## Description

I want to create a Remaining Tasks Radial Gauge using the Telerik UI for .NET MAUI [Radial Gauge](https://www.telerik.com/maui-ui/gauge) component. This gauge should display three task categories (blue, yellow, and red), each represented by a pair of indicators overlapping one another. The lighter indicator represents the total range, while the darker one represents the current value.

This knowledge base article also answers the following questions:
- How to use GaugeBarIndicator for a Remaining Tasks Radial Gauge in .NET MAUI?
- What is the XAML code for a Radial Gauge with overlapping indicators?
- How to create a radial gauge with adjustable values using sliders?

## Solution

To create a Remaining Tasks Radial Gauge, use overlapping `GaugeBarIndicator` elements. Each task category (e.g., blue, yellow, and red) consists of a pair of indicators: one for the full range and one for the current value. Follow this step-by-step guide:

1. Add the necessary color resources for each task category.
2. Configure the `RadRadialGauge` with a `GaugeLinearAxis` and indicators.
3. Use sliders to adjust the values dynamically.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
             x:Class="TelerikMauiApp1.MainPage">

    <ContentPage.Resources>
        <Color x:Key="LightBlue">#9ECFFA</Color>
        <Color x:Key="DarkBlue">#0E88F2</Color>
        <Color x:Key="LightYellow">#FFDEB1</Color>
        <Color x:Key="DarkYellow">#FFAC3E</Color>
        <Color x:Key="LightRed">#FF9999</Color>
        <Color x:Key="DarkRed">#FF0000</Color>
    </ContentPage.Resources>

    <Grid RowDefinitions="*, Auto, Auto">
        <telerik:RadRadialGauge x:Name="MyGauge"
                                Margin="2"
                                AxisRadiusFactor="1"
                                StartAngle="90"
                                SweepAngle="360"
                                WidthRequest="300"
                                HeightRequest="300"
                                Grid.Row="0">
            <telerik:RadRadialGauge.Axis>
                <telerik:GaugeLinearAxis Maximum="100"
                                         Minimum="0"
                                         ShowLabels="False"
                                         StrokeThickness="0" />
            </telerik:RadRadialGauge.Axis>
            <telerik:RadRadialGauge.Indicators>
                <!-- BLUE -->
                <telerik:GaugeBarIndicator EndThickness="20"
                                           Fill="{StaticResource LightBlue}"
                                           StartThickness="20"
                                           Offset="3"
                                           Value="100" />
                <telerik:GaugeBarIndicator x:Name="BlueBarIndicator"
                                           EndCap="Oval"
                                           StartCap="Oval"
                                           Fill="{StaticResource DarkBlue}"
                                           EndThickness="20"
                                           StartThickness="20"
                                           Offset="3"
                                           Value="12.5" />
                <!-- YELLOW -->
                <telerik:GaugeBarIndicator EndThickness="20"
                                           Fill="{StaticResource LightYellow}"
                                           StartThickness="20"
                                           Offset="25"
                                           Value="100" />
                <telerik:GaugeBarIndicator x:Name="YellowBarIndicator"
                                           EndCap="Oval"
                                           StartCap="Oval"
                                           EndThickness="20"
                                           Fill="{StaticResource DarkYellow}"
                                           StartThickness="20"
                                           Offset="25"
                                           Value="37.5" />
                <!-- RED -->
                <telerik:GaugeBarIndicator EndThickness="20"
                                           Fill="{StaticResource LightRed}"
                                           StartThickness="20"
                                           Offset="47"
                                           Value="100" />
                <telerik:GaugeBarIndicator x:Name="RedBarIndicator"
                                           EndCap="Oval"
                                           StartCap="Oval"
                                           EndThickness="20"
                                           Fill="{StaticResource DarkRed}"
                                           StartThickness="20"
                                           Offset="47"
                                           Value="62.5" />
            </telerik:RadRadialGauge.Indicators>
        </telerik:RadRadialGauge>

        <StackLayout Orientation="Horizontal" 
                     Grid.Row="1" 
                     HorizontalOptions="Center" 
                     Margin="20">
            <Rectangle Fill="{StaticResource DarkBlue}"
                       WidthRequest="20"
                       HeightRequest="20"
                       Margin="5"/>
            <Label Text="Blue" 
                   VerticalOptions="Center" 
                   Margin="0,0,10,0"/>
            <Rectangle Fill="{StaticResource DarkYellow}"
                       WidthRequest="20"
                       HeightRequest="20"
                       Margin="5"/>
            <Label Text="Yellow"
                   VerticalOptions="Center" 
                   Margin="0,0,10,0"/>
            <Rectangle Fill="{StaticResource DarkRed}"
                       WidthRequest="20"
                       HeightRequest="20"
                       Margin="5"/>
            <Label Text="Red"
                   VerticalOptions="Center" 
                   Margin="0,0,10,0"/>
        </StackLayout>

        <StackLayout Grid.Row="2" 
                     Margin="10"
                     WidthRequest="300"
                     Spacing="3">
            <telerik:RadSlider x:Name="BlueSlider"
                               Minimum="0"
                               Maximum="100"
                               Value="{Binding Value, Source={x:Reference BlueBarIndicator}, Mode=TwoWay}" 
                               RangeTrackFill="{StaticResource DarkBlue}" />
            <telerik:RadSlider x:Name="YellowSlider"
                               Minimum="0"
                               Maximum="100"
                               Value="{Binding Value, Source={x:Reference YellowBarIndicator}, Mode=TwoWay}" 
                               RangeTrackFill="{StaticResource DarkYellow}" />
            <telerik:RadSlider x:Name="RedSlider"
                               Minimum="0"
                               Maximum="100"
                               Value="{Binding Value, Source={x:Reference RedBarIndicator}, Mode=TwoWay}" 
                               RangeTrackFill="{StaticResource DarkRed}"/>
        </StackLayout>
    </Grid>
</ContentPage>
```

## See Also

- [Radial Gauge Overview](https://www.telerik.com/maui-ui/gauge)
- [Radial Gauge Indicators](https://www.telerik.com/maui-ui/documentation/controls/gauge/indicators#bar-indicator)
- [Gauge Ranges](https://www.telerik.com/maui-ui/documentation/controls/gauge/ranges)
- [.NET MAUI Gauge Positioning](https://www.telerik.com/maui-ui/documentation/controls/gauge/positioning)
