---
title: Customize ChartTooltipBehavior in Chart for .NET MAUI
description: Learn how to format the tooltip in Chart for .NET MAUI.
type: how-to
page_title: Customizing ChartTooltipBehavior in Chart for .NET MAUI
slug: customize-chart-tooltip-net-maui
tags: [.net maui, chart, tooltip, customization, template]
res_type: kb
---

## Environment

| Property | Value |
|----------|-------|
| Product  | Chart for .NET MAUI |

## Description

I want to customize the ChartTooltipBehavior in Chart for .NET MAUI.

## Solution

To customize the tooltip in the NET MAUI Chart, you can use the native Chart implementation of the different platforms (Android and iOS):

1. Subscribe to the `HandlerChanged` event of the chart.
2. Use the native chart objects to customize the tooltip on Android and iOS platforms.

Here is an example of how to customize the tooltip:

```csharp
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

For Android, you must define a `MyTooltipContentAdapter` class inside the `Platforms/Android` folder:

```csharp
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

For iOS, define the `MyChartDelegate` class inside the `Platforms/iOS` folder:

```csharp
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

- With the native approach, you won't be able to bind properties from the page's View Model. You will have access to the data points and their data.
- Make sure to replace the placeholder class names and namespaces with your actual class names and namespaces.

## See Also

- [Chart for .NET MAUI Documentation](https://docs.telerik.com/devtools/maui-ui/controls/chart/chart-overview)
