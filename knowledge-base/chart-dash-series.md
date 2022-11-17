---
title: Chart: Dashed line series
description: Modify the line chart to have dashed lines by using the native chart.
type: how-to
page_title: Dashed line chart
slug: chart-dash-series
position: 
tags: MAUI
ticketid: 1582451
res_type: kb
---

## Environment
<table>
	<tbody>
		<tr>
			<td>Product Version</td>
			<td>3.2.1</td>
		</tr>
		<tr>
			<td>Product</td>
			<td>Chart for .NET MAUI</td>
		</tr>
	</tbody>
</table>


## Description

In this article I will show you how to define a stroke for the Line Series Chart to change its appearance to that of a Dashed Chart.

## Solution

This solution uses the Native Chart Classes and their respective property/method for DashedArray to achieve the desired Dashed Line Series behavior.

## Code

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
        var platformView = this.chart.Handler.PlatformView;
#if ANDROID
        var platformChart = (Com.Telerik.Widget.Chart.Visualization.CartesianChart.RadCartesianChartView)platformView;
        var platformSeries = (Com.Telerik.Widget.Chart.Visualization.CartesianChart.Series.Categorical.LineSeries)platformChart.Series.Get(1);
        platformSeries.SetDashArray(new float[2] { 10, 20 });
#elif IOS || MACCATALYST
        var platformChart = (Telerik.Maui.Controls.Compatibility.ChartRenderer.iOS.TKExtendedChart)platformView;
		var platformSeries = (TelerikUI.TKChartLineSeries)platformChart.Series[1];
        var stroke = new TelerikUI.TKStroke(UIKit.UIColor.Blue);
        stroke.DashPattern = new Foundation.NSNumber[] { new Foundation.NSNumber(10), new Foundation.NSNumber(20) };
        platformSeries.Style.Stroke = stroke;
#elif WINDOWS
        var platformChart = (Telerik.UI.Xaml.Controls.Chart.RadCartesianChart)platformView;
        var platformSeries = (Telerik.UI.Xaml.Controls.Chart.LineSeries)platformChart.Series[1];
        platformSeries.StrokeDashArray = new Microsoft.UI.Xaml.Media.DoubleCollection { 10, 20 };
#endif
    }
}
```

## Final Result

![Chart Palette](images/dashedchart-mac.png)