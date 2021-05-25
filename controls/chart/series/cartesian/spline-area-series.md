---
title: SplineArea Series
page_title: .NET MAUI Chart Documentation | SplineArea Series
description: Check our &quot;SplineArea Series&quot; documentation article for Telerik Chart for .NET MAUI
slug: chart-series-spline-area-series
position: 0
---

# SplineArea Series

## Overview

**RadCartesianChart** visualizes **SplineAreaSeries** as an area on the chart that is enclosed by the coordinate axes and straight line segments that connect the data points represented by these series. The **SplineAreaSeries** extend **CategoricalStrokedSeries**, so they are also **CategoricalSeries** and require one **CategoricalAxis** and one **NumricalAxis**.

## Features

- **Stroke** (Color): changes the color used to draw lines.
- **StrokeThickness** (double): changes the width of the lines.
- **Fill** (Color): changes the color used to fill the area shapes.

## Example

Here is an example how to create RadCartesianChart with SplineArea Series:

First, create the needed business objects, for example:

```C#
public class CategoricalData
{
    public object Category { get; set; }

    public double Value { get; set; }
}
```

Then create a ViewModel:

```C#
public class CategoricalViewModel
{
    public ObservableCollection<CategoricalData> Data { get; set; }

    public CategoricalViewModel()
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

Finally, use the following snippet to declare a RadCartesianChart with SplineArea Series in XAML and in C#:

```XAML
<telerikChart:RadCartesianChart>
    <telerikChart:RadCartesianChart.BindingContext>
        <local:CategoricalViewModel />
    </telerikChart:RadCartesianChart.BindingContext>
    <telerikChart:RadCartesianChart.HorizontalAxis>
        <telerikChart:CategoricalAxis LabelFitMode="MultiLine"
                                      PlotMode="OnTicks" />
    </telerikChart:RadCartesianChart.HorizontalAxis>
    <telerikChart:RadCartesianChart.VerticalAxis>
        <telerikChart:NumericalAxis />
    </telerikChart:RadCartesianChart.VerticalAxis>
    <telerikChart:RadCartesianChart.Series>
        <telerikChart:SplineAreaSeries ValueBinding="Value"
                                       CategoryBinding="Category"
                                       ItemsSource="{Binding Data}" />
    </telerikChart:RadCartesianChart.Series>
</telerikChart:RadCartesianChart>
```

And here is the result:

![Basic SplineAreaSeries](images/cartesian-spline-area-series-basic-example.png)

### Customization Example

```C#
	var series = new SplineAreaSeries 
	{ 
		Stroke = new Color(0.6, 0.6, 0.9), 
		StrokeThickness = 5, 
		Fill = new Color(0.8, 0.8, 1) 
	};
```
![Customized SplineAreaSeries](images/cartesian-spline-area-series-customization-example.png)

## See Also

- [Line Series]({%slug chart-series-line-series%})
- [ScatterLine Series]({%slug chart-series-scatter-line-series%})
- [Spline Series]({%slug chart-series-spline-series%})
