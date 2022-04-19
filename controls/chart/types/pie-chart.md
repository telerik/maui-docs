---
title: Pie Chart
page_title: .NET MAUI Chart Documentation | Pie Chart
position: 2
description: Check our &quot;Pie Chart&quot; documentation article for Telerik Chart for .NET MAUI
previous_url: /controls/chart/types/chart-types-pie-chart
slug: chart-types-pie-chart
---

# Pie Chart

The Pie Chart visualizes its data points by using the radial coordinate system. Each data point is represented as a slice from a pie. The ratio between the space consumed by each slice and the space consumed by the whole chart is the same as the ratio between the value of the data point that it represents and the total value of all data points in the series.

## Properties

The Pie Chart supports the following properties:

* `Series`&mdash;Gets a collection of all series presented by the chart instance.
* `Behaviors`&mdash;Gets a collection of all enabled behaviors.
* `Palette`&mdash;Gets or sets the `ChartPalette` instance that defines the appearance of the chart.
* `PaletteName`&mdash;Gets or sets the name of the predefined `Palette` that will be applied to the chart.
* `SelectionPalette`&mdash;Gets or sets the `ChartPalette` instance that defines the appearance of the chart for the selected series and/or data points.
* `SelectionPaletteName`&mdash;Gets or sets the name of the predefined `SelectionPalette` that will be applied to the chart.

## Series

The Pie Chart supports the Pie Series, which visualize a single series of data in a pie chart. The sweep of a pie slice is directly proportional to the magnitude of the data point values.

## Example

1. Define the `RadPieChart`:  

 ```XAML
<telerikChart:RadPieChart>
</telerikChart:RadPieChart>
 ```

1. Add the series to the `RadPieChart.Series` collection:

 ```XAML
<telerikChart:RadPieChart.Series>
	<telerikChart:PieSeries ItemsSource="{Binding Data}">
		<telerikChart:PieSeries.ValueBinding>
			<telerikChart:PropertyNameDataPointBinding PropertyName="Value"/>
		</telerikChart:PieSeries.ValueBinding>
	</telerikChart:PieSeries>
</telerikChart:RadPieChart.Series>
 ```

1. Set the `BindingContext` of the chart if none of its parents has a context:

 ```XAML
<telerikChart:RadPieChart.BindingContext>
	<local:ViewModel/>
</telerikChart:RadPieChart.BindingContext>
```


## Pie Chart Example

The following example shows the full definition of the chart.

1. First, create the needed business object, for example:

 ```C#
public class CategoricalData
{
    public object Category { get; set; }

    public double Value { get; set; }
}
 ```

1. Then, create a `ViewModel`:

 ```C#
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

1. Finally, declare a `RadPieChart` with a Pie Series in XAML and in C#:

 ```XAML
<telerikChart:RadPieChart>
    <telerikChart:RadPieChart.BindingContext>
        <local:ViewModel />
    </telerikChart:RadPieChart.BindingContext>
    <telerikChart:RadPieChart.Series>
        <telerikChart:PieSeries ShowLabels="True"
                                RadiusFactor="0.8"
                                ValueBinding="Value"
                                ItemsSource="{Binding Data}" />
    </telerikChart:RadPieChart.Series>
</telerikChart:RadPieChart>
 ```


The following image shows the end result:

![Pie Chart](images/pie-chart-example.png)

## See Also

- [Cartesian Chart]({%slug chart-types-cartesian-chart%})
- [Chart Legend]({%slug chart-features-legend%})
- [Chart Null Values]({%slug chart-nullvalues%})
