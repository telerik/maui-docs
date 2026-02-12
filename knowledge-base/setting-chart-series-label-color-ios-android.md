---
title: Setting Chart Series Label Color for iOS and Android
description: Learn how to set the Chart Series Label color in UI for .NET MAUI for iOS and Android platforms.
type: how-to
page_title: Changing BarSeries Label Color in UI for .NET MAUI Chart
meta_title: Changing BarSeries Label Color in UI for .NET MAUI Chart
slug: setting-chart-series-label-color-ios-android
tags: chart, ui for .net maui, series, labels, color, ios, android
res_type: kb
ticketid: 1709714
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 12.1.0 | Telerik UI for .NET MAUI Chart | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to change the color of the labels displayed on a [BarSeries](https://www.telerik.com/maui-ui/documentation/controls/chart/series/cartesian/bar-series) in UI for .NET MAUI Chart for iOS and Android platforms. Changing the label color requires platform-specific customization by accessing the native chart control.

This knowledge base article also answers the following questions:
- How to customize label text color in the BarSeries for iOS and Android.
- How to change the point label style for BarSeries in UI for .NET MAUI Chart.
- How to set platform-specific properties for Chart labels in UI for .NET MAUI.

## Solution

To set the Chart Series Label color for iOS and Android platforms, follow these steps:

1. Define your chart in XAML:
    ```xaml
    <Grid RowDefinitions="*">
        <telerik:RadCartesianChart x:Name="MyChart"
                                   HandlerChanged="Chart_HandlerChanged">
            <telerik:RadCartesianChart.HorizontalAxis>
                <telerik:DateTimeContinuousAxis LabelTextColor="Blue" />
            </telerik:RadCartesianChart.HorizontalAxis>
            <telerik:RadCartesianChart.VerticalAxis>
                <telerik:NumericalAxis LabelTextColor="Red"/>
            </telerik:RadCartesianChart.VerticalAxis>
            <telerik:RadCartesianChart.Series>
                <telerik:BarSeries  ItemsSource="{Binding Data}"
                                    CategoryBinding="Date"
                                    ShowLabels="True"
                                    ValueBinding="Value" />
            </telerik:RadCartesianChart.Series>
        </telerik:RadCartesianChart>
    </Grid>
    ```

2. Use the `HandlerChanged` event to access the native chart control and customize the label colors. Implement the following code in your code-behind:

    ```csharp
    private void Chart_HandlerChanged(object sender, EventArgs e)
    {
        var platformView = MyChart?.Handler?.PlatformView;

        #if IOS
        var platformChart = (Telerik.Maui.Controls.Compatibility.ChartRenderer.iOS.TKExtendedChart)platformView;
        var platformSeries = (TelerikUI.TKChartColumnSeries)platformChart.Series.First();
        platformSeries.Style.PointLabelStyle.TextColor = UIKit.UIColor.Red;
        #elif ANDROID
        var platformChart = (Com.Telerik.Widget.Chart.Visualization.CartesianChart.RadCartesianChartView)platformView;
        var platformSeries = (Com.Telerik.Widget.Chart.Visualization.CartesianChart.Series.Categorical.BarSeries)platformChart.Series.Get(0);
        platformSeries.LabelFillColor = Android.Graphics.Color.Red;
        platformSeries.LabelTextColor = Android.Graphics.Color.Blue;
        #endif
    }
    ```

3. Define your data model and view model:

    ```csharp
    public class TemporalData
    {
        public DateTime Date { get; set; }
        public double Value { get; set; }
    }

    public class ViewModel
    {
        public ObservableCollection<TemporalData> Data { get; set; } = GetDateTimeData(10);

        private static ObservableCollection<TemporalData> GetDateTimeData(int itemsCount)
        {
            var items = new ObservableCollection<TemporalData>();
            var startDate = new DateTime(2015, 03, 01);
            var rand = new Random();

            for (var i = 0; i < itemsCount; i++)
            {
                items.Add(new TemporalData
                {
                    Date = startDate.AddMinutes(i),
                    Value = rand.NextDouble() * (0.5 - 0.3) + 0.3
                });
            }

            return items;
        }
    }
    ```

## See Also

- [UI for .NET MAUI Chart Overview](https://www.telerik.com/maui-ui/documentation/controls/chart/overview)
