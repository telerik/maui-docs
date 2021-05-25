---
title: ScatterSpline Series
page_title: .NET MAUI Chart Documentation | ScatterSpline Series
description: Check our &quot;ScatterSpline Series&quot; documentation article for Telerik Chart for .NET MAUI
slug: chart-series-scatter-spline-series
position: 0
---

# ScatterSplineSeries #

## Overview ##

The **ScatterSplineSeries** are represented on the chart as data points connected with curved line segments. The **ScatterSplineSeries** inherit from the[**ScatterPointSeries**]({% slug chart-series-scatter-point-series %}) class and also require both axes of the chart to be of type **NumericalAxis**.

## Features ##

- **Stroke** (Color): changes the color used to draw lines.
- **StrokeThickness** (double): changes the width of the lines.


## Example ##

Here is an example how to create RadCartesianChart with ScatterSpline Series:

First, create the needed business objects, for example:

```C#
public class NumericalData
{
    public double XData { get; set; }
    public double YData { get; set; }
}
```

Then create a ViewModel:

```C#
public class SeriesNumericalViewModel
{
    public ObservableCollection<NumericalData> Data1 { get; set; }
    public ObservableCollection<NumericalData> Data2 { get; set; }

    public SeriesNumericalViewModel()
    {
        this.Data1 = GetNumericData1();
        this.Data2 = GetNumericData2();
    }

    public static ObservableCollection<NumericalData> GetNumericData1()
    {
        var data = new ObservableCollection<NumericalData>
        {
            new NumericalData { XData = 2, YData = 13 },
            new NumericalData { XData = 19, YData = 31 },
            new NumericalData { XData = 22, YData = 33 },
            new NumericalData { XData = 28, YData = 35 },
            new NumericalData { XData = 33, YData = 46 },
            new NumericalData { XData = 38, YData = 34 },
            new NumericalData { XData = 49, YData = 66 },
            new NumericalData { XData = 55, YData = 24 },
            new NumericalData { XData = 62, YData = 41 },
        };
        return data;
    }
    public static ObservableCollection<NumericalData> GetNumericData2()
    {
        var data = new ObservableCollection<NumericalData>
        {
            new NumericalData { XData = 7, YData = 13 },
            new NumericalData { XData = 19, YData = 17 },
            new NumericalData { XData = 22, YData = 19 },
            new NumericalData { XData = 28, YData = 21 },
            new NumericalData { XData = 33, YData = 35 },
            new NumericalData { XData = 38, YData = 43 },
            new NumericalData { XData = 49, YData = 15 },
            new NumericalData { XData = 55, YData = 21 },
            new NumericalData { XData = 62, YData = 47 },
        };
        return data;
    }
}
```

Finally, use the following snippet to declare a RadCartesianChart with ScatterSpline Series in XAML:

```XAML
<telerikChart:RadCartesianChart>
    <telerikChart:RadCartesianChart.BindingContext>
        <local:SeriesNumericalViewModel />
    </telerikChart:RadCartesianChart.BindingContext>
    <telerikChart:RadCartesianChart.HorizontalAxis>
        <telerikChart:NumericalAxis LabelFitMode="MultiLine" />
    </telerikChart:RadCartesianChart.HorizontalAxis>
    <telerikChart:RadCartesianChart.VerticalAxis>
        <telerikChart:NumericalAxis />
    </telerikChart:RadCartesianChart.VerticalAxis>
    <telerikChart:RadCartesianChart.Series>
        <telerikChart:ScatterSplineSeries XValueBinding="XData"
                                          YValueBinding="YData"
                                          ItemsSource="{Binding Data1}" />
        <telerikChart:ScatterSplineSeries XValueBinding="XData"
                                          YValueBinding="YData"
                                          ItemsSource="{Binding Data2}" />
    </telerikChart:RadCartesianChart.Series>
</telerikChart:RadCartesianChart>
```

And here is the result:
	
![Basic ScatterSplineSeries](images/cartesian-scatter-spline-series-basic-example.png)

### Customization Example

```C#
	var series = new ScatterSplineSeries 
	{ 
		Stroke = new Color(0.6, 0.6, 0.9), 
		StrokeThickness = 5 
	};
```
## See Also

- [Line Series]({%slug chart-series-line-series%})
- [ScatterLine Series]({%slug chart-series-scatter-line-series%})
- [Spline Series]({%slug chart-series-spline-series%})
