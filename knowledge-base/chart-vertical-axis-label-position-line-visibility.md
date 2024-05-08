---
title: Vertical Axis Label Position on iOS Same as on Android
description: Learn how to position the y axis labels on left and display the axis line on iOS Chart for .NET MAUI.
type: how-to
page_title: iOS Chart - Y Axis Labels Position and Line Visibility
slug: chart-vertical-axis-label-position-line-visibility
position: 
tags: chart, axis, vertical axis, label position, android, ios, maui, dotnetmaui
ticketid: 1630605
res_type: kb
---

## Environment
| Version | Product | Author | 
| --- | --- | ---- | 
| 6.6.0 | Telerik UI for .NET MAUI Chart | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 


## Description

The differences in the position of the vertical axis labels are caused by the fact that the native Android and iOS Charts are two different controls and their appearance isn't always the same on all platforms.

To further customize the `RadChart` control, use the native Chart. This article shows how to position the Vertical Axis Labels on iOS on the left and make them mimic Android.

![.NET MAUI Chart iOS Y axis customization](images/chart-vertical-axes-label-position-ios.png)

## Solution

**1.** Define the needed business objects:

```C#
public class CategoricalData
{
    public object Category { get; set; }

    public double Value { get; set; }
}
```

**2.** Create a sample ViewModel:

```C#
public class CategoricalDataViewModel
{
    public ObservableCollection<CategoricalData> Data { get; set; }

    public CategoricalDataViewModel()
    {
        this.Data = GetCategoricalData();
    }

    private static ObservableCollection<CategoricalData> GetCategoricalData()
    {
        var data = new ObservableCollection<CategoricalData>
        {
            new CategoricalData { Category = "A", Value = 101 },
            new CategoricalData { Category = "B", Value = 45 },
            new CategoricalData { Category = "C", Value = 77 },
            new CategoricalData { Category = "D", Value = 15 },
            new CategoricalData { Category = "E", Value = 56 },
        };
        return data;
    }
}
```

**3.** Define the Chart control in XAML:

```XAML
<telerik:RadCartesianChart x:Name="chart">
    <telerik:RadCartesianChart.BindingContext>
        <local:CategoricalDataViewModel />
    </telerik:RadCartesianChart.BindingContext>
    <telerik:RadCartesianChart.HorizontalAxis>
        <telerik:CategoricalAxis LabelFitMode="MultiLine"
                                 PlotMode="OnTicks" />
    </telerik:RadCartesianChart.HorizontalAxis>
    <telerik:RadCartesianChart.VerticalAxis>
        <telerik:NumericalAxis />
    </telerik:RadCartesianChart.VerticalAxis>
    <telerik:RadCartesianChart.Series>
        <telerik:LineSeries ValueBinding="Value"
                            CategoryBinding="Category"
                            ItemsSource="{Binding Data}" />
    </telerik:RadCartesianChart.Series>
</telerik:RadCartesianChart>
```

**4.** Access the native Chart by subscribing to the `HandlerChanged`event:

```C#
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
