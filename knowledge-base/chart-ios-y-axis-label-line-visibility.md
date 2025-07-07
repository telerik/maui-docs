---
title: Achieving Consistent Chart Rendering Across Android and iOS
description: Learn how to achieve consistent rendering for CartesianChart in .NET MAUI between Android and iOS, including fixing Y-axis line visibility and label alignment.
type: how-to
page_title: Fixing Y-Axis Line and Label Alignment in Chart for iOS
meta_title: Fixing Y-Axis Line and Label Alignment in Chart for iOS
slug: chart-ios-y-axis-label-line-visibility
tags: chart,.net maui,radcartesianchart,axis,handler
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.0 | Telerik UI for .NET MAUI Chart | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to achieve consistent rendering for the [Chart](https://docs.telerik.com/devtools/maui/controls/chart/types/cartesian-chart) in .NET MAUI across Android and iOS. On iOS, the Y-axis line is not visible, and the axis labels are inside the chart renderer and right-aligned instead of left-aligned as on Android.

This knowledge base article also answers the following questions:
- How to make the Y-axis line visible in `RadCartesianChart` for iOS?
- How to align the Y-axis labels to the left in `RadCartesianChart` for iOS?
- How to customize the `RadCartesianChart` rendering for iOS in .NET MAUI?

## Solution

Access the native iOS chart control via the handler to customize the Y-axis line visibility and label alignment.

1. Subscribe to the `HandlerChanged` event of `RadCartesianChart`.
2. Access the native iOS control in the event handler.
3. Modify the Y-axis properties to make the line visible and align the labels to the left.

```csharp
<telerik:RadCartesianChart x:Name="chart" />

public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        this.BindingContext = new SeriesCategoricalViewModel();

        this.chart.HandlerChanged += this.Chart_HandlerChanged;
    }

    private void Chart_HandlerChanged(object sender, EventArgs e)
    {
        this.UpdateChart();
    }

    private void UpdateChart()
    {
        var platformView = this.chart.Handler.PlatformView;
#if IOS || MACCATALYST
        var platformChart = (Telerik.Maui.Controls.Compatibility.ChartRenderer.iOS.TKExtendedChart)platformView;
        platformChart.YAxis.Style.LineHidden = false;
        platformChart.YAxis.Style.LabelStyle.TextAlignment = TelerikUI.TKChartAxisLabelAlignment.Left;
        platformChart.YAxis.Style.LabelStyle.FirstLabelTextAlignment = TelerikUI.TKChartAxisLabelAlignment.Left;
#endif
    }
}
```

## See Also

- [CartesianChart Overview](https://docs.telerik.com/devtools/maui/controls/chart/types/cartesian-chart)
- [Customizing Native Chart Controls in .NET MAUI](https://docs.telerik.com/devtools/maui/search?q=chart)
