---
title: Annotations
page_title: .NET MAUI Chart Documentation | Annotations
description: Check our &quot;Annotations&quot; documentation article for Telerik Chart for .NET MAUI.
tags: .net maui, chart, ui for .net maui
position: 7
slug: chart-annotations
---

# Annotations 

## Overview

**Annotations** are visual elements used to highlight certain areas on the plot. They can be used as comments or as markers for specific values on the plot. You can practically use any visual element as a template for the annotation.

RadChart provides support for the following types of annotations:

- **Cartesian GridLineAnnotations**: this annotation is visually represented by straight lines across the chart that marks a specific value on the associated Cartesian axis.
- **Cartesian PlotBandAnnotations**: this annotation is visually represented by a band across the chart that marks a specific range on the associated Cartesian axis.

## CartesianGridLineAnnotation

The **CartesianGridLineAnnotation** represents a vertical or horizontal line that crosses the entire plot area.

### Features

- **Axis** : the CartesianGridLineAnnotation should be associated with horizontal or vertical cartesian axis explicitly.
- **Value** : the place on the associated axis where a line crosses it.

> Note: When the associated axis is numerical - a numeric value is expected, and when it is a CategoricalAxis - a category is expected. 

### Example

Here is an example of how the CartesianGridLineAnnotation works:

First, create the needed business objects:

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
    public double Threshold { get; set; }

    public ViewModel()
    {
        this.Data = GetCategoricalData();
        this.Threshold = this.Data.Average(data => data.Value);
    }

    private static ObservableCollection<CategoricalData> GetCategoricalData()
    {
        var data = new ObservableCollection<CategoricalData>
        {
            new CategoricalData { Category = "Greenings", Value = 21 },
            new CategoricalData { Category = "Perfecto", Value = 18 },
            new CategoricalData { Category = "NearBy", Value = 44 },
            new CategoricalData { Category = "Family", Value = 77 },
            new CategoricalData { Category = "Fresh", Value = 34 },
        };
        return data;
    }
}
```

Finally, use the following snippet to declare the RadChart in XAML:

```XAML
<telerikChart:RadCartesianChart>
    <telerikChart:RadCartesianChart.BindingContext>
        <local:ViewModel />
    </telerikChart:RadCartesianChart.BindingContext>
    <telerikChart:RadCartesianChart.HorizontalAxis>
        <telerikChart:CategoricalAxis LabelFitMode="MultiLine" />
    </telerikChart:RadCartesianChart.HorizontalAxis>
    <telerikChart:RadCartesianChart.VerticalAxis>
        <telerikChart:NumericalAxis x:Name="verticalAxis" />
    </telerikChart:RadCartesianChart.VerticalAxis>
    <telerikChart:RadCartesianChart.Series>
        <telerikChart:BarSeries ValueBinding="Value"
                                CategoryBinding="Category"
                                ItemsSource="{Binding Data}" />
    </telerikChart:RadCartesianChart.Series>
    <telerikChart:RadCartesianChart.Annotations>
        <telerikChart:CartesianGridLineAnnotation Stroke="#0E72F6" 
                                                  StrokeThickness="2"
                                                  Axis="{x:Reference verticalAxis}"
                                                  Value="{Binding Threshold}">
            <telerikChart:CartesianGridLineAnnotation.DashArray>
                <x:Array Type="{x:Type x:Double}">
                    <x:Double>4.0</x:Double>
                    <x:Double>2.0</x:Double>
                </x:Array>
            </telerikChart:CartesianGridLineAnnotation.DashArray>
        </telerikChart:CartesianGridLineAnnotation>
    </telerikChart:RadCartesianChart.Annotations>
</telerikChart:RadCartesianChart>
```

Here is how the CartesianGridLineAnnotation looks:

![Annotations](images/chart-annotations-grid-line-examples.png)

## CartesianPlotBandAnnotation

The **CartesianPlotBandAnnotation** represents a vertical or horizontal area that crosses the entire plot area.  

### Features

- **Axis** : the cartesian plotband annotation needs to be associated with horizontal or vertical axis explicitly.
- **From** : the starting value for the plotband.
- **To** : the ending value for the plotband.
- **Fill** :  Gets or sets the Fill. 

### Example

Here is an example of how the CartesianPlotBandAnnotation works:

First, create the needed business objects:

```C#
public class CategoricalData
{
    public object Category { get; set; }

    public double Value { get; set; }
}
```

The ViewModel:

```C#
public class ViewModel
{
    public ObservableCollection<CategoricalData> Data { get; set; }
    public double StartThreshold { get; private set; }
    public double EndThreshold { get; private set; }

    public ViewModel()
    {
        this.Data = GetCategoricalData();
        var threshold = this.Data.Average(data => data.Value);
        this.StartThreshold = threshold * 0.9;
        this.EndThreshold = threshold * 1.1;
    }

    private static ObservableCollection<CategoricalData> GetCategoricalData()
    {
        var data = new ObservableCollection<CategoricalData>
        {
            new CategoricalData { Category = "Greenings", Value = 66 },
            new CategoricalData { Category = "Perfecto", Value = 19 },
            new CategoricalData { Category = "NearBy", Value = 92 },
            new CategoricalData { Category = "Family", Value = 23 },
            new CategoricalData { Category = "Fresh", Value = 56 },
        };
        return data;
    }
}
```

Finally, use the following snippet to declare the RadChart control in XAML:

```XAML
<telerikChart:RadCartesianChart>
    <telerikChart:RadCartesianChart.BindingContext>
        <local:ViewModel />
    </telerikChart:RadCartesianChart.BindingContext>
    <telerikChart:RadCartesianChart.HorizontalAxis>
        <telerikChart:CategoricalAxis LabelFitMode="MultiLine"
                                      PlotMode="OnTicks" />
    </telerikChart:RadCartesianChart.HorizontalAxis>
    <telerikChart:RadCartesianChart.VerticalAxis>
        <telerikChart:NumericalAxis x:Name="verticalAxis" />
    </telerikChart:RadCartesianChart.VerticalAxis>
    <telerikChart:RadCartesianChart.Series>
        <telerikChart:LineSeries ValueBinding="Value"
                                 CategoryBinding="Category"
                                 ItemsSource="{Binding Data}" />
    </telerikChart:RadCartesianChart.Series>
    <telerikChart:RadCartesianChart.Annotations>
        <telerikChart:CartesianPlotBandAnnotation StrokeThickness="2"
                                                  Stroke="Green"
                                                  Fill="#2F66FF33"
                                                  Axis="{x:Reference verticalAxis}"
                                                  From="{Binding StartThreshold}"
                                                  To="{Binding EndThreshold}" />
    </telerikChart:RadCartesianChart.Annotations>
</telerikChart:RadCartesianChart>
```

Here is how the CartesianPlotBandAnnotation looks:

![Annotations](images/chart-annotations-plot-band-example.png)

## See Also

- [CartesianChart Grid]({%slug cartesian-chart-grid%})
- [Chart Legend]({%slug chart-features-legend%})
- [Chart Null Values]({%slug chart-nullvalues%})
