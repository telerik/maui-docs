---
title: Area Series
page_title: .NET MAUI Chart Documentation | Area Series
description: Check our &quot;Area Series&quot; documentation article for Telerik Chart for .NET MAUI control.
slug: chart-series-area-series
position: 0
---

# Area Series

## Overview

**RadCartesianChart** visualizes **AreaSeries** as an area on the chart that is enclosed by the coordinate axes and straight line segments that connect the data points represented by these series. The **AreaSeries** extend **CategoricalStrokedSeries**, so they are also **CategoricalSeries** and require one **CategoricalAxis** and one **NumricalAxis**.

## Features

- **Fill** : Defines the fill of the AreaSeries.
- **Stroke** : Changes the color used to draw lines.
- **StrokeThickness** : Changes the width of the lines.

## Example

Here is an example how to create RadCartesianChart with Area Series:

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

Finally, use the following snippet to declare a RadCartesianChart with Area Series in XAML and in C#:

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
        <telerikChart:AreaSeries ValueBinding="Value"
                                 CategoryBinding="Category"
                                 ItemsSource="{Binding Data}" />
    </telerikChart:RadCartesianChart.Series>
</telerikChart:RadCartesianChart>
```

Here is the result:

![Basic AreaSeries](images/cartesian-area-series-basic-example.png)

### Customization Example

Here we have some customizations:
```C#
	var series = new AreaSeries 
	{ 
		Fill = new Color(0.8, 0.8, 1),
		Stroke = new Color(0.6, 0.6, 0.9), 
		StrokeThickness = 5
	};
```

This is the final result:

![Customized AreaSeries](images/cartesian-area-series-customization-example.png)

## See Also

- [Bar Series]({%slug chart-series-bar-series%})
- [Line Series]({%slug chart-series-line-series%})
- [Spline Series]({%slug chart-series-spline-series%})