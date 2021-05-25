---
title: Pie Chart
page_title: .NET MAUI Chart Documentation | Pie Chart
position: 2
description: Check our &quot;Pie Chart&quot; documentation article for Telerik Chart for .NET MAUI
slug: chart-types-pie-chart
---

# RadPieChart #

The **RadPieChart**  visualizes its data points using radial coordinate system. Each data point is represented as a slice from a pie. The ratio between the space consumed by each slice and the space consumed by the whole chart is the same as the ratio between the value of the data point that it represents and the total value of all data points in the series.

## Properties

* **Series**: Gets a collection of all series presented by the chart instance.
* **Behaviors**: Gets a collection of all enabled behaviors.
* **Palette**: Gets or sets the **ChartPalette** instance that defines the appearance of the chart.
* **PaletteName**: Gets or sets the name of the predefined Palette that will be applied to the chart.
* **SelectionPalette**: Gets or sets the **ChartPalette** instance that defines the appearance of the chart for selected series and/or data points.
* **SelectionPaletteName**: Gets or sets the name of the predefined SelectionPalette that will be applied to the chart.

## Supported Series ##

**RadPieChart** can visualize the following types of series:

- **PieSeries**: The PieSeries are used to visualize a single series of data in a pie chart. The sweep of a pie's slices is directly proportional to the magnitude of the data points' values.

## Example ##

1. Define RadPieChart:  
	
```XAML
<telerikChart:RadPieChart>
</telerikChart:RadPieChart>
```

2. After that you can add the series to the RadPieChart.Series collection:

```XAML
<telerikChart:RadPieChart.Series>
	<telerikChart:PieSeries ItemsSource="{Binding Data}">
		<telerikChart:PieSeries.ValueBinding>
			<telerikChart:PropertyNameDataPointBinding PropertyName="Value"/>
		</telerikChart:PieSeries.ValueBinding>
	</telerikChart:PieSeries>
</telerikChart:RadPieChart.Series>
```

3. You also have to set a BindingContext of the chart if none of its parents have a context:
 
```XAML
<telerikChart:RadPieChart.BindingContext>
	<local:ViewModel/>
</telerikChart:RadPieChart.BindingContext>
```

### PieChart Example

Here is the full definition of the chart:

First, create the needed business object, for example:

```C#
public class CategoricalData
{
    public object Category { get; set; }

    public double Value { get; set; }
}
```

Then create a ViewModel:

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

Finally use the following snippet to declare a RadPieChart with Pie Series in XAML and in C#:

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

Here is the result:

![Pie Chart](images/pie-chart-example.png)

## See Also

- [Cartesian Chart]({%slug chart-types-cartesian-chart%})
- [Chart Legend]({%slug chart-features-legend%})
- [Chart Null Values]({%slug chart-nullvalues%})
