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

The native Android and iOS chart controls can render the Y-axis differently. On iOS, the Y-axis line is not visible, and the axis labels are inside the chart renderer and right-aligned instead of left-aligned as on Android.

This article shows how to customize the native iOS chart control to make the Y-axis line visible and align the labels to the left.

## Solution

Start with a configured .NET MAUI app that includes the Telerik XAML namespace and a `RadCartesianChart`. The following XAML fragment defines the chart and its vertical axis:

```XAML
<telerik:RadCartesianChart x:Name="chart">
    <telerik:RadCartesianChart.VerticalAxis>
        <telerik:NumericalAxis />
    </telerik:RadCartesianChart.VerticalAxis>
</telerik:RadCartesianChart>
```

In the page code-behind, subscribe to the `HandlerChanged` event and update the native chart when its handler is available:

```C#
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        this.chart.HandlerChanged += this.Chart_HandlerChanged;
    }

    private void Chart_HandlerChanged(object sender, EventArgs e)
    {
        this.UpdateChart();
    }

    private void UpdateChart()
    {
#if IOS || MACCATALYST
        var platformView = this.chart.Handler?.PlatformView;
        if (platformView == null)
        {
            return;
        }

        var platformChart = (Telerik.Maui.Controls.Compatibility.ChartRenderer.iOS.TKExtendedChart)platformView;
        platformChart.YAxis.Style.LineHidden = false;
        platformChart.YAxis.Style.LabelStyle.TextAlignment = TelerikUI.TKChartAxisLabelAlignment.Left;
        platformChart.YAxis.Style.LabelStyle.FirstLabelTextAlignment = TelerikUI.TKChartAxisLabelAlignment.Left;
#endif
    }
}
```

Run the app on iOS and verify that the Y-axis line is visible and the labels are left-aligned. The conditional compilation keeps the iOS-specific API out of Android builds.

## See Also

- [CartesianChart Overview]({%slug chart-types-cartesian-chart%})
- [Chart Overview]({%slug chart-overview%})
