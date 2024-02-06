---
title: Change the Position of the Labels Inside the Bar Series and Customize the Vertical Axis
description: Learn how to change the position of the labels inside the bar series and customize the vertical axis for Telerik MAUI Chart on WinUI.
type: how-to
page_title: Change Label Position for Bar Series and Customize the Vertical Axis 
slug: chart-bar-series-winui-label-position
position: 
tags: maui, chart, labels, bar series, position
ticketid: 1612671
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 6.7.0 | Telerik UI for .NET MAUI Chart |[Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 


## Description

How to change the position of the labels inside the bar series and customize the vertical axis? 

## Solution

To customize the chart vertical axis and to change the position of the labels inside the bar series, use the native [Chart for WinUI](https://docs.telerik.com/devtools/winui/controls/radchart/overview).

**1.** Define the Chart in XAML:

```XAML
<Grid RowDefinitions="*">
    <telerik:RadCartesianChart x:Name="barChart" 
                                HandlerChanged="barChart_HandlerChanged">
        <telerik:RadCartesianChart.BindingContext>
            <local:ViewModel />
        </telerik:RadCartesianChart.BindingContext>
        <telerik:RadCartesianChart.HorizontalAxis>
            <telerik:CategoricalAxis LabelFitMode="MultiLine" 
                                        PlotMode="BetweenTicks" />
        </telerik:RadCartesianChart.HorizontalAxis>
        <telerik:RadCartesianChart.VerticalAxis>
            <telerik:NumericalAxis LabelFitMode="MultiLine" 
                                    MajorTickThickness="0"
                                    ShowLabels="False" />
        </telerik:RadCartesianChart.VerticalAxis>
        <telerik:RadCartesianChart.Series>
            <telerik:BarSeries ValueBinding="Value"
            CategoryBinding="Category" ShowLabels="True" 
            ItemsSource="{Binding Data}" />
        </telerik:RadCartesianChart.Series>
        <telerik:RadCartesianChart.ChartBehaviors>
            <telerik:ChartTooltipBehavior TriggerMode="Tap" />
        </telerik:RadCartesianChart.ChartBehaviors>
    </telerik:RadCartesianChart>
</Grid>
```

**2.** Add sample data and view model:

```C#
public class CategoricalData
{
    public object Category { get; set; }
    public double Value { get; set; }
}
public class ViewModel
{
    public ObservableCollection<CategoricalData> Data { get; set; }

    public ViewModel()
    {
        this.Data = GetCategoricalData();
    }

    private static ObservableCollection<CategoricalData> GetCategoricalData()
    {
        var data = new ObservableCollection<CategoricalData>
        {
            new CategoricalData { Category = "Greenings", Value = 52 },
            new CategoricalData { Category = "Perfecto", Value = 19 },
            new CategoricalData { Category = "NearBy", Value = 82 },
            new CategoricalData { Category = "Family", Value = 23 },
            new CategoricalData { Category = "Fresh", Value = 56 },
        };
        return data;
    }
}
```

**3.** Subscribe to chart `HandlerChanged` event to access the native control:

```C#
private void barChart_HandlerChanged(object sender, EventArgs e)
{
    var platformView = this.barChart.Handler.PlatformView;
#if WINDOWS
    var platformChart = (Telerik.UI.Xaml.Controls.Chart.RadCartesianChart)platformView;
    var series = (Telerik.UI.Xaml.Controls.Chart.BarSeries)platformChart.Series[0];
    // style the vertical axis. The resource is inside the Platforms/Windows/App.xaml file
    platformChart.VerticalAxis.LineStyle = MauiWinUIApplication.Current.Resources["VerticalAxisStyle"] as Microsoft.UI.Xaml.Style;
    
    // customize the labels for the bar series, for example change their position
    var labelDefinition = series.LabelDefinitions.FirstOrDefault();
    if (labelDefinition != null)
    {
        labelDefinition.HorizontalAlignment = Microsoft.UI.Xaml.HorizontalAlignment.Center;
        labelDefinition.VerticalAlignment = Microsoft.UI.Xaml.VerticalAlignment.Top;
    }
#endif
}
```

**4.** The style resource is inside the **Platforms/Windows/App.xaml** file:

```C#
<Style TargetType="Line" x:Key="VerticalAxisStyle">
    <Setter Property="Stroke" Value="Red"/>
    <Setter Property="StrokeDashArray" Value="2 2"/>
</Style>
```
