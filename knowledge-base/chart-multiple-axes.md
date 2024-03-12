---
title: Creating Charts with Multiple Axes
page_title: Creating Charts with Multiple Horizontal and Vertical Axes - .NET MAUI Knowledge Base
description: Learn how to create a Telerik UI for .NET MAUI Chart component showing two vertical and a horizontal axis at the same time.
type: how-to
slug: chart-multiple-axis
tags: maui, chart, axis, multiple axis, second axis, vertical axis
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 4.0.0 | Telerik UI for .NET MAUI Chart | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 


## Description

How can I create a chart with multiple axes when I want to add a second horizontal or vertical axis?

## Solution

You can use one of the following options for applying multiple axis on a chart.

### Using a Chart with Two Series

Use chart with two series. 

**1.** Define a sample chart in XAML:

```XAML
<telerik:RadCartesianChart x:Name="chart" HandlerChanged="chart_HandlerChanged">
    <telerik:RadCartesianChart.HorizontalAxis>
        <telerik:CategoricalAxis ShowLabels="True" />
    </telerik:RadCartesianChart.HorizontalAxis>
    <telerik:RadCartesianChart.VerticalAxis>
        <telerik:NumericalAxis Location="Left" Minimum="-10" Maximum="110" MajorStep="10"
                            ShowLabels="True"/>
    </telerik:RadCartesianChart.VerticalAxis>
    <telerik:RadCartesianChart.Series>
        <telerik:LineSeries CategoryBinding="Category"
                        ValueBinding="Value"
                        ShowLabels="True"
                        ItemsSource="{Binding Data1}" />

        <telerik:LineSeries CategoryBinding="Category"
            ValueBinding="Value"
            ShowLabels="True"
            ItemsSource="{Binding Data2}" />
    </telerik:RadCartesianChart.Series>
</telerik:RadCartesianChart>
```

**2.** Define the `ViewModel` and `CategoricalData` model:

```C#
public class CategoricalData
{
    public object Category { get; set; }
    public double Value { get; set; }
}

public class SeriesCategoricalViewModel
{
    public ObservableCollection<CategoricalData> Data1 { get; set; }
    public ObservableCollection<CategoricalData> Data2 { get; set; }

    public SeriesCategoricalViewModel()
    {
        this.Data1 = GetCategoricalData1();
        this.Data2 = GetCategoricalData2();
    }

    private static ObservableCollection<CategoricalData> GetCategoricalData1()
    {
        var data = new ObservableCollection<CategoricalData>
        {
            new CategoricalData { Category = "Greenings", Value = 52 },
            new CategoricalData { Category = "Perfecto", Value = 19 },
            new CategoricalData { Category = "NearBy", Value = 82 },
            new CategoricalData { Category = "Family", Value = 23 },
            new CategoricalData { Category = "Fresh", Value = -2 },
        };
        return data;
    }

    private static ObservableCollection<CategoricalData> GetCategoricalData2()
    {
        var data = new ObservableCollection<CategoricalData>
        {
            new CategoricalData { Category = "Greenings", Value = 33 },
            new CategoricalData { Category = "Perfecto", Value = 51 },
            new CategoricalData { Category = "NearBy", Value = 11 },
            new CategoricalData { Category = "Family", Value = 94 },
            new CategoricalData { Category = "Fresh", Value = 12 },
        };
        return data;
    }
}

```

Subscribe to the `Chart.HandlerChanged` event. Inside the event, access the native chart per platform and add additional vertical axis to the native control.

```C#
private void chart_HandlerChanged(object sender, EventArgs e)
{
    this.UpdateChart();
}

private void UpdateChart()
{
    var platformView = this.chart.Handler.PlatformView;
#if ANDROID
    var platformChart = (Com.Telerik.Widget.Chart.Visualization.CartesianChart.RadCartesianChartView)platformView;
    var platformSeries = (Com.Telerik.Widget.Chart.Visualization.CartesianChart.Series.Categorical.LineSeries)platformChart.Series.Get(1);
    AddSecondaryVerticalAxis(platformSeries);

#elif IOS || MACCATALYST
    var platformChart = (Telerik.Maui.Controls.Compatibility.ChartRenderer.iOS.TKExtendedChart)platformView;
    var platformSeries = (TelerikUI.TKChartLineSeries)platformChart.Series[1];
    TelerikUI.TKChartNumericAxis tKChartNumericAxis = new TelerikUI.TKChartNumericAxis();
    tKChartNumericAxis.Position = TelerikUI.TKChartAxisPosition.Left;
    platformChart.AddAxis(tKChartNumericAxis);
    platformSeries.YAxis = tKChartNumericAxis;

#elif WINDOWS
    var platformChart = (Telerik.UI.Xaml.Controls.Chart.RadCartesianChart)platformView;
    var platformSeries = (Telerik.UI.Xaml.Controls.Chart.LineSeries)platformChart.Series[1];
    var vertical = platformSeries.VerticalAxis = new Telerik.UI.Xaml.Controls.Chart.LinearAxis();
    vertical.HorizontalLocation = Telerik.Charting.AxisHorizontalLocation.Left;
#endif
}


#if ANDROID

private void AddSecondaryVerticalAxis(Java.Lang.Object lineSeries)
{
    if (lineSeries is Com.Telerik.Widget.Chart.Visualization.CartesianChart.Series.Categorical.LineSeries)
    {
        var series = lineSeries as Com.Telerik.Widget.Chart.Visualization.CartesianChart.Series.Categorical.LineSeries;

        Com.Telerik.Widget.Chart.Visualization.CartesianChart.Axes.LinearAxis verticalAxisBar = new Com.Telerik.Widget.Chart.Visualization.CartesianChart.Axes.LinearAxis();
        verticalAxisBar.HorizontalLocation = Com.Telerik.Widget.Chart.Engine.Axes.Common.AxisHorizontalLocation.Left;
        series.VerticalAxis = verticalAxisBar;
    }
}

#endif
}
```

**Approach 2**

Create two separate Charts together and add a transparent background to the top chart.

>important By using the Axis `Location` property, you can specify the axis position. The supported options are Right` and `Left` for vertical axes, and `Top` and `Bottom` for horizontal axes.

The following example shows the XAML code for implementing the suggested approach:

```XAML
<Grid>
    <!-- bottom chart -->
    <telerik:RadCartesianChart x:Name="chart" >
        <telerik:RadCartesianChart.HorizontalAxis>
            <telerik:CategoricalAxis ShowLabels="True" />
        </telerik:RadCartesianChart.HorizontalAxis>
        <telerik:RadCartesianChart.VerticalAxis>
            <telerik:NumericalAxis Location="Right"
                                   ShowLabels="True"/>
        </telerik:RadCartesianChart.VerticalAxis>
        <telerik:RadCartesianChart.Series>
            <telerik:LineSeries CategoryBinding="Category"
                                ValueBinding="Value"
                                ShowLabels="True"
                                ItemsSource="{Binding Data}" />
        </telerik:RadCartesianChart.Series>
    </telerik:RadCartesianChart>

    <!-- top chart -->
    <telerik:RadCartesianChart x:Name="chart2"
                               BackgroundColor="Transparent">
        <telerik:RadCartesianChart.HorizontalAxis>
            <telerik:CategoricalAxis LabelTextColor="Transparent"
                                     LineColor="Transparent"
                                     ShowLabels="False"/>
        </telerik:RadCartesianChart.HorizontalAxis>
        <telerik:RadCartesianChart.VerticalAxis>
            <telerik:NumericalAxis ShowLabels="True"/>
        </telerik:RadCartesianChart.VerticalAxis>
        <telerik:RadCartesianChart.Series>
            <telerik:LineSeries CategoryBinding="Category"
                                ValueBinding="Value"
                                ShowLabels="True"
                                ItemsSource="{Binding Data1}" />
        </telerik:RadCartesianChart.Series>
    </telerik:RadCartesianChart>
</Grid>
```
