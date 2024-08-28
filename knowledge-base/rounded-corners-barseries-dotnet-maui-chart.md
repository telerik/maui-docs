---
title: Applying Rounded Corners to BarSeries in .NET MAUI Chart
description: Learn how to customize the BarSeries in a CartesianChart for .NET MAUI by applying rounded corners through platform-specific configurations.
type: how-to
page_title: How to Customize BarSeries with Rounded Corners in .NET MAUI Chart
slug: rounded-corners-barseries-dotnet-maui-chart
tags: chart, .net maui, customization, barseries, rounded corners
res_type: kb
---

## Environment

| Product | Version | Author |
| --- | --- | --- |
| Chart for .NET MAUI | 7.1.0 |  [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

When implementing a `RadCartesianChart` with `BarSeries` in a .NET MAUI application, you might want to customize the appearance of the bar series to have rounded corners. This customization is not available directly through the Chart's API and requires accessing the native Chart elements on Android and iOS to apply the desired styling.

This KB article also answers the following questions:
- How can I customize the appearance of BarSeries in .NET MAUI Chart?
- Is it possible to apply rounded corners to bars in a .NET MAUI Chart?
- Can I access native Chart properties for customization in .NET MAUI?

## Solution

To apply rounded corners to `BarSeries` in a `RadCartesianChart` for .NET MAUI, follow these steps:

**1.** Define the Chart in XAML and subscribe to the `HandlerChanged` event:

```xml
<telerik:RadCartesianChart x:Name="chart"
                           HandlerChanged="chart_HandlerChanged">
    <telerik:RadCartesianChart.BindingContext>
        <local:CategoricalDataViewModel />
    </telerik:RadCartesianChart.BindingContext>
    <telerik:RadCartesianChart.HorizontalAxis>
        <telerik:CategoricalAxis LabelFitMode="MultiLine" />
    </telerik:RadCartesianChart.HorizontalAxis>
    <telerik:RadCartesianChart.VerticalAxis>
        <telerik:NumericalAxis LabelFitMode="MultiLine" />
    </telerik:RadCartesianChart.VerticalAxis>
    <telerik:RadCartesianChart.Series>
        <telerik:BarSeries ValueBinding="Value"
                    CategoryBinding="Category"
                    ItemsSource="{Binding Data}" />
    </telerik:RadCartesianChart.Series>
</telerik:RadCartesianChart>
```

**2.** Implement the `ViewModel` and sample data model as per your data requirements:

```csharp
public class CategoricalData
{
    public object Category { get; set; }
    public double Value { get; set; }
}
public class CategoricalDataViewModel
{
    public ObservableCollection<CategoricalData> Data { get; set; }

    public CategoricalDataViewModel()
    {
        this.Data = new ObservableCollection<CategoricalData>
        {
            new CategoricalData { Category = "A", Value = 101 },
            new CategoricalData { Category = "B", Value = 45 },
            new CategoricalData { Category = "C", Value = 77 },
            new CategoricalData { Category = "D", Value = 15 },
            new CategoricalData { Category = "E", Value = 56 },
        };
    }
}
```

**3.** Implement the `HandlerChanged` event handler to customize the bar series on each platform.

```csharp
private void chart_HandlerChanged(object sender, EventArgs e)
{
    this.UpdateChart();
}

private void UpdateChart()
{
    var platformView = this.chart.Handler.PlatformView;
#if ANDROID
    var platformChart = (Com.Telerik.Widget.Chart.Visualization.CartesianChart.RadCartesianChartView)platformView;
    var platformSeries = (Com.Telerik.Widget.Chart.Visualization.CartesianChart.Series.Categorical.BarSeries)platformChart.Series.Get(0);
    platformSeries.AreBarsRounded = true;
    platformSeries.RoundBarsRadius = 10;
#elif IOS
    var platformiOSChart = (Telerik.Maui.Controls.Compatibility.ChartRenderer.iOS.TKExtendedChart)platformView;
    var platformSeries = (TelerikUI.TKChartBarSeries)platformiOSChart.Series[0];
    platformSeries.Style.Palette = new TelerikUI.TKChartPalette();
    var paletteItem = new TelerikUI.TKChartPaletteItem();
    paletteItem.Fill = new TelerikUI.TKSolidFill(UIKit.UIColor.Red, 5.0f);
    paletteItem.Stroke = new TelerikUI.TKStroke(UIKit.UIColor.Black);
    platformSeries.Style.Palette.AddPaletteItem(paletteItem);
#endif
}
```

## Notes

- The customization process involves platform-specific code, which requires conditional compilation directives (`#if ANDROID` and `#if IOS`) to apply the correct styling for each platform.
