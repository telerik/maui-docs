---
title: Customizing Chart Tooltips in .NET MAUI
description: Learn how to customize Chart tooltips in Telerik UI for .NET MAUI with ChartTooltipBehavior or platform-specific native APIs for advanced appearance changes.
type: how-to
page_title: Customizing Chart Tooltips in Chart for .NET MAUI
slug: customize-chart-tooltip-net-maui
tags: [.net maui, chart, tooltip, customization, template]
res_type: kb
---

## Environment

| Property | Value |
|----------|-------|
| Product  | Chart for .NET MAUI |
| Platforms | Android and iOS |

## Description

I want to customize the tooltips in the Chart for .NET MAUI on Android and iOS.

## Solution

The examples assume a configured `RadCartesianChart`. If you need to set up the chart first, follow [the CartesianChart getting started guide]({%slug charts-cartesian-getting-started%}).

Use the cross-platform `ChartTooltipBehavior` API for standard tooltip content and styling. See [Customizing CartesianChart tooltips]({%slug charts-cartesian-tooltip%}) for the supported cross-platform API.

For platform-specific customization that the cross-platform API does not expose, use the native chart implementation for Android and iOS.

1. Subscribe to the `HandlerChanged` event of the chart.
2. Use the native chart objects to customize the tooltip on Android and iOS platforms.

The following code-behind fragment accesses the native chart after its handler is created:

```C#
private void chart_HandlerChanged(object sender, EventArgs e)
{
    var platformView = this.chart.Handler.PlatformView;

#if ANDROID
    var platformChart = (Com.Telerik.Widget.Chart.Visualization.CartesianChart.RadCartesianChartView)platformView;
    Com.Telerik.Widget.Chart.Visualization.Behaviors.ChartTooltipBehavior tooltip = (Com.Telerik.Widget.Chart.Visualization.Behaviors.ChartTooltipBehavior)platformChart.Behaviors.Get(0);
    tooltip.SetContentAdapter(new Platforms.Android.MyTooltipContentAdapter());
#elif IOS
    var platformiOSChart = (Telerik.Maui.Controls.Compatibility.ChartRenderer.iOS.TKExtendedChart)platformView;
    platformiOSChart.Trackball.Tooltip.Style.Fill = new TelerikUI.TKSolidFill()
    {
        Color = new UIKit.UIColor(red: 1.00f, green: 0.75f, blue: 0.87f, alpha: 1.00f),
        ShadowBlur = 0.3f,
        ShadowColor =   new UIKit.UIColor(red: 1.00f, green: 0.75f, blue: 0.87f, alpha: 1.00f),
        Alpha = 0.9f,
    };

    platformiOSChart.Trackball.Tooltip.Style.TextColor = UIKit.UIColor.DarkGray;
    platformiOSChart.Delegate = new Platforms.iOS.MyChartDelegate(this.chart);
#endif
}
```

### Android Specifics

For Android, define the `MyTooltipContentAdapter` class inside the `Platforms/Android/` folder. This fragment implements the native tooltip content adapter:

```C#
public class MyTooltipContentAdapter : Java.Lang.Object, Com.Telerik.Android.Primitives.Widget.Tooltip.Contracts.ITooltipContentAdapter
{
    public bool ApplyDefaultStyles { get; set; }
    public Com.Telerik.Android.Common.IFunction CategoryToStringConverter { get; set; }
    public Com.Telerik.Android.Common.IFunction ValueToStringConverter { get; set; }

    public global::Android.Views.View GetView(Java.Lang.Object[] p0)
    {
        global::Android.Content.Context context = MauiApp2.MainApplication.Context;
        global::Android.Widget.LinearLayout linearLayout = new global::Android.Widget.LinearLayout(context);
        linearLayout.Orientation = global::Android.Widget.Orientation.Vertical;
        linearLayout.SetBackgroundColor(global::Android.Graphics.Color.LightSalmon);
        linearLayout.SetPadding(10, 10, 10, 10);

        foreach (Com.Telerik.Widget.Chart.Engine.DataPoints.CategoricalDataPoint dataPoint in p0)
        {
            global::Android.Widget.TextView textView = new global::Android.Widget.TextView(context);
            textView.Text = string.Format("Value of {0} is $ {1}", dataPoint.Category, dataPoint.Value);
            linearLayout.AddView(textView);
        }
        return linearLayout;
    }
}
```

### iOS Specifics

For iOS, define the `MyChartDelegate` class inside the `Platforms/iOS/` folder. This fragment overrides the native trackball selection callback:

```C#
public class MyChartDelegate : Telerik.Maui.Controls.Compatibility.ChartRenderer.iOS.CartesianChartDelegate
{
    public MyChartDelegate(RadCartesianChart chart) : base(chart)
    {
    }

    public override void TrackballDidTrackSelection(TKChart chart, TKChartSelectionInfo[] selection)
    {
        StringBuilder str = new StringBuilder();
        bool first = true;
        foreach (TelerikUI.TKChartSelectionInfo info in selection)
        {
            var point = info.DataPoint as TelerikUI.TKChartDataPoint;
            if (!first)
            {
                str.Append("\n");
            }
            else
            {
                first = !first;
            }
            str.Append(string.Format("Value of {0} is $ {1}", point.DataXValue, point.DataYValue));
        }
        chart.Trackball.Tooltip.Text = str.ToString();
    }
}
```

## Notes

The native approach does not support binding properties from the page's view model. You can access the data points and their data instead.

Replace the placeholder class names and namespaces with the class names and namespaces from your app.

## See Also

* [Chart for .NET MAUI overview]({%slug chart-overview%})
* [Customizing CartesianChart tooltips]({%slug charts-cartesian-tooltip%})
