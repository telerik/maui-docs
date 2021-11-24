---
title: Area Series
page_title: .NET MAUI Chart Documentation | Area Series
description: Check our &quot;Area Series&quot; documentation article for Telerik Chart for .NET MAUI control.
slug: chart-series-area-series
position: 0
---

# Area Series

The Cartesian Chart visualizes the Area Series as an area on the chart that is enclosed by the coordinate axes and straight line segments that connect the data points represented by these series. The Area Series extend the Categorical Stroked Series, so they are also Categorical Series and require one Categorical Axis and one Numerical Axis.

## Features

The Area Series supports the following properties:

- `Fill`&mdash;Defines the fill of the Area Series.
- `Stroke`&mdash;Changes the color for drawing lines.
- `StrokeThickness`&mdash;Changes the width of the lines.

## Area Series Example

The following example shows how to create a Cartesian Chart with an Area Series:

1. First, create the needed business objects, for example:

 ```C#
public class CategoricalData
{
    public object Category { get; set; }

    public double Value { get; set; }
}
 ```

1. Then create a `ViewModel`:

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

1. Finally, use the following snippet to declare a Cartesian Chart with an Area Series in XAML and in C#:

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

The following image shows the end result:

![Basic AreaSeries](images/cartesian-area-series-basic-example.png)

## Customization Example

You can further customize the Area Series:

```C#
	var series = new AreaSeries
	{
		Fill = new Color(0.8, 0.8, 1),
		Stroke = new Color(0.6, 0.6, 0.9),
		StrokeThickness = 5
	};
```

The following image shows the final result:

![Customized AreaSeries](images/cartesian-area-series-customization-example.png)

## See Also

- [Bar Series]({%slug chart-series-bar-series%})
- [Line Series]({%slug chart-series-line-series%})
- [Spline Series]({%slug chart-series-spline-series%})
