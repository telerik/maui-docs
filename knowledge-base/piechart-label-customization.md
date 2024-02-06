---
title: Customizing Labels in the Pie Chart
page_title: Customizing Pie Charts Labels - .NET MAUI Knowledge Base
description: Learn how to customize the Telerik UI for .NET MAUI Pie Chart labels.
type: how-to
slug: piechart-label-customization
tags: maui, chart, axis, piechart, label, customization, text, color
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 6.7.0 | Telerik UI for .NET MAUI Chart | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 


## Description

How can I customize the labels in the Pie Chart, for example, set the text color, font size, an so on?

## Solution

To customize the labels in the Pie Chart, use the native Pie Chart for Android, iOS, or WinUI.

**1.** Add sample model and view model:

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

**2.** Define the Pie Chart in XAML:

```XAML
<Grid RowDefinitions="*">
    <telerik:RadPieChart x:Name="chart" 
                         HandlerChanged="chart_HandlerChanged">
        <telerik:RadPieChart.BindingContext>
            <local:ViewModel />
        </telerik:RadPieChart.BindingContext>
        <telerik:RadPieChart.Series>
            <telerik:PieSeries ShowLabels="True"
                        RadiusFactor="0.4"
                        ValueBinding="Value" LabelFormat="C"
                        ItemsSource="{Binding Data}" />
        </telerik:RadPieChart.Series>
    </telerik:RadPieChart>
</Grid>
```

**3.** Subscribe to the `HandlerChanged` event:

```C#
private void chart_HandlerChanged(object sender, EventArgs e)
{
    this.UpdateChart();
}
```

**4.** And inside the `UpdateChart()` method, implement the custom logic for accessing the native Android, iOS, or WinUI Chart and customize the labels of the `PieSeries`:

```C#
private void UpdateChart()
{
    var platformView = this.chart.Handler.PlatformView;
#if WINDOWS
    var platformChart = (Telerik.UI.Xaml.Controls.Chart.RadPieChart)platformView;
    var series = platformChart.Series[0];
    // Remove the default labels.
    series.LabelDefinitions.Clear();
    // Add a custom label with a custom template.
    series.LabelDefinitions.Add(new Telerik.UI.Xaml.Controls.Chart.ChartSeriesLabelDefinition
    {
        // The label template definition is added inside the Platforms/Windows/App.xaml file: 
        LabelTemplate = MauiWinUIApplication.Current.Resources["CustomLabelTemplate"] as Microsoft.UI.Xaml.DataTemplate
    });

#elif ANDROID

    var platformChart = (Com.Telerik.Widget.Chart.Visualization.PieChart.RadPieChartView)platformView;
    var series = platformChart.Series.ToArray()?.FirstOrDefault() as Com.Telerik.Widget.Chart.Visualization.PieChart.PieSeries;
    if(series != null) 
    {
        // To remove the percentage, set the following format:
        series.LabelFormat = "%.2f";
            
        // Then, draw a new label and further customize it inside the CustomPieSeriesLabelRenderer class (Platforms/Android folder).
        series.LabelRenderer = new Platforms.Android.CustomPieSeriesLabelRenderer(series);
    }


#elif IOS || MACCATALYST
    var platformChart = (Telerik.Maui.Controls.Compatibility.ChartRenderer.iOS.TKExtendedChart)platformView;
    // Render a new label using the Delegate.
    platformChart.Delegate = new Platforms.iOS.MyChartDelegate(this.chart);
#endif
}
```

**5.** For WinUI, add the label template definition inside the `Platforms/Windows/App.xaml` file:

```XAML
<maui:MauiWinUIApplication.Resources>
    <DataTemplate x:Key="CustomLabelTemplate">
        <Grid>
            <!-- You can apply color, font size, and other properties available for the TextBlock element. --> 
            <TextBlock Text="{Binding DataItem.Value}" FontSize="30" Foreground="Red" />
        </Grid>
    </DataTemplate>
</maui:MauiWinUIApplication.Resources>
```

**6.** For Android, create a class `CustomPieSeriesLabelRenderer` inside the `Platforms/Android` folder. This class is used for native label rendering:

```C#
using Android.Graphics;
using Android.Runtime;
using Com.Telerik.Widget.Chart.Engine.ElementTree;
using Com.Telerik.Widget.Chart.Visualization.PieChart;
using Color = Android.Graphics.Color;
using Paint = Android.Graphics.Paint;
using Path = Android.Graphics.Path;

namespace MauiApp1.Platforms.Android
{
    class CustomPieSeriesLabelRenderer : PieSeriesLabelRenderer
    {
        private readonly Paint strokePaint = new Paint();

        protected CustomPieSeriesLabelRenderer(IntPtr javaReference, JniHandleOwnership transfer)
            : base(javaReference, transfer)

        {
        }

        public CustomPieSeriesLabelRenderer(Com.Telerik.Widget.Chart.Visualization.PieChart.PieSeries p0)
            : base(p0)
        {
        }


        public override void RenderLabel(Canvas canvas, ChartNode node)
        {
            this.strokePaint.Color = Color.Transparent;
            LabelStrokePaint = strokePaint;
            this.LabelTextColor = Color.Black;
            base.RenderLabel(canvas, node);
        }

        protected override void DrawLabelText(Canvas canvas, string text, float p2, float p3)
        {
            base.DrawLabelText(canvas, text, p2, p3);
        }

        protected override void DrawLabelBackground(Canvas canvas, Path path, int p2)
        {
            base.DrawLabelBackground(canvas, path, p2);
        }

        protected override Paint GetLabelFillPaint(int p0)
        {
            return base.GetLabelFillPaint(p0);
        }
    }
}

```

**7.** For iOS and MacCatalyst, render a new label using a delegate. Create a class `MyChartDelegate` inside the `Platforms/iOS` and `Platforms/MacCatalyst` folders:

```C#
using Telerik.Maui.Controls.Compatibility.Chart;
using TelerikUI;
using UIKit;

namespace MauiApp1.Platforms.iOS
{
    public class MyChartDelegate : Telerik.Maui.Controls.Compatibility.ChartRenderer.iOS.PieChartDelegate
    {
        public MyChartDelegate(RadPieChart chart) : base(chart)
        {
        }
        public override TKChartPointLabel LabelForDataPoint(TKChart chart, TKChartData dataPoint, string propertyName, TKChartSeries series, nuint dataIndex)
        {
            TKChartDataPoint chartDataPoint = (TKChartDataPoint)dataPoint;
            return new MyChartPointLabel(chartDataPoint, series, chartDataPoint.DataXValue.ToString());
        }
    }

    public class MyChartPointLabel : TKChartPointLabel
    {
        public MyChartPointLabel(TKChartDataPoint point, TKChartSeries series, string text) : base(point, series, text)
        {
            this.Style.TextColor = UIColor.White;
        }
    }
}
```