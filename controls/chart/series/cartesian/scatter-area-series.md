---
title: Scatter Area
page_title: .NET MAUI Chart Documentation | Scatter Area Series
description: Check our &quot;ScatterArea Series&quot; documentation article for Telerik Chart for .NET MAUI
slug: chart-series-scatter-area-series
position: 0
---

# Scatter Area Series

The Cartesian Chart visualizes the Scatter Area Series as the area enclosed by the coordinate axes and straight line segments that connect the series data points. The Scatter Area Series inherit from the `[ScatterPointSeries]()` class and also require both Chart axes to be Numerical Axes.

## Features

The Scatter Area Series provides the following properties to change its style:

- `Stroke` (Color)&mdash;Changes the color for drawing lines.
- `StrokeThickness` (double)&mdash;Changes the width of the lines.
- `Fill` (Color)&mdash;Changes the color of the chart area.

## Scatter Area Series Example

The following example shows how to create a `RadCartesianChart` with a Scatter Area Series:

1. First, create the needed business objects, for example:

 ```C#
public class NumericalData
{
    public double XData { get; set; }
    public double YData { get; set; }
}
 ```

1. Then, create a `ViewModel`:

 ```C#
public class NumericalViewModel
{
    public ObservableCollection<NumericalData> Data { get; set; }

    public NumericalViewModel()
    {
        this.Data = GetNumericData();
    }

    public static ObservableCollection<NumericalData> GetNumericData()
    {
        var data = new ObservableCollection<NumericalData>
        {
            new NumericalData { XData = 4, YData = 9 },
            new NumericalData { XData = 8, YData = 10 },
            new NumericalData { XData = 9, YData = 13 },
            new NumericalData { XData = 12, YData = 24 },
            new NumericalData { XData = 17, YData = 24 },
            new NumericalData { XData = 21, YData = 4 },
            new NumericalData { XData = 26, YData = 13 },
            new NumericalData { XData = 29, YData = 3 },
            new NumericalData { XData = 30, YData = 16 },
        };
        return data;
    }
}
 ```

1. Finally, use the following snippet to declare a Cartesian Chart with a Scatter Area Series in XAML:

 ```XAML
<telerikChart:RadCartesianChart>
    <telerikChart:RadCartesianChart.BindingContext>
        <local:NumericalViewModel />
    </telerikChart:RadCartesianChart.BindingContext>
    <telerikChart:RadCartesianChart.HorizontalAxis>
        <telerikChart:NumericalAxis LabelFitMode="MultiLine" />
    </telerikChart:RadCartesianChart.HorizontalAxis>
    <telerikChart:RadCartesianChart.VerticalAxis>
        <telerikChart:NumericalAxis />
    </telerikChart:RadCartesianChart.VerticalAxis>
    <telerikChart:RadCartesianChart.Series>
        <telerikChart:ScatterAreaSeries XValueBinding="XData"
                                        YValueBinding="YData"
                                        ItemsSource="{Binding Data}" />
    </telerikChart:RadCartesianChart.Series>
</telerikChart:RadCartesianChart>
 ```

The following image shows the end result:

![Basic ScatterAreaSeries](images/cartesian-scatter-area-series-basic-example.png)

## Customization Example

You can further customize the Scatter Area Series:

```C#
	var series = new ScatterAreaSeries
	{
		Stroke = new Color(0.6, 0.6, 0.9),
		StrokeThickness = 5,
		Fill = new Color(0.8, 0.8, 1)
	};
```

## See Also

- [Line Series]({%slug chart-series-line-series%})
- [ScatterLine Series]({%slug chart-series-scatter-line-series%})
- [ScatterPoint Series]({%slug chart-series-scatter-point-series%})
