---
title: Scatter Series
page_title: .NET MAUI Cartesian Chart Documentation - Scatter Series
description: Learn how to create scatter point, scatter line, and scatter area charts with the Telerik UI for .NET MAUI Cartesian Chart by combining the PointSeries, LineSeries, and AreaSeries with two numerical axes.
components: ["charts"]
tags: charts, cartesian chart, series, scatter, scatter point, scatter line, scatter area, xy chart, numerical axis, .net maui
position: 5
slug: charts-cartesian-scatter-series
---

# .NET MAUI Cartesian Chart Scatter Series

The scatter series is a combination of a series type and two numerical axes. Use the following series with two `NumericalAxis` instances to render scatter charts:

* [`PointSeries`]({% slug charts-cartesian-point-series %}) 
* [`LineSeries`]({% slug charts-cartesian-line-series %}) 
* [`AreaSeries`]({% slug charts-cartesian-area-series %}) 
* [`SplineAreaSeries`]({% slug charts-cartesian-spline-area-series %})

## Data Binding

To configure a scatter series:

1. Set the chart's horizontal and vertical axes to `NumericalAxis`.
1. Set the series `ItemsSource` to a collection of data items with two numeric members.
1. Set `HorizontalBinding` to the member that provides the X value.
1. Set `VerticalBinding` to the member that provides the Y value.

## Line and Area Customization

Use the following properties to customize the appearance of the line and area:

* `Fill` (`Brush`)&mdash;Defines the fill of the area (applicable for `AreaSeries` and `SplineAreaSeries`).
* `Stroke` (`Brush`)&mdash;Defines the brush to paint the stroke of the line or area.
* `StrokeThickness` (`double`)&mdash;Defines the thickness of the line or area stroke.

## Labels Customization

Use the following properties to configure the labels visualized for each data point:

* `ShowLabels` (`bool`)&mdash;Defines whether the axis labels will be displayed.
* `LabelOffset` (`Size`)&mdash;Defines the offset of the labels from the line or area.
* `LabelStyle` (`Style` with target type `ChartLabelAppearance`)&mdash;Defines the style of the axis labels.

## Example

The following example shows how to plot a `PointSeries` and a `LineSeries` as scatter series against two numerical axes.

1. Define the data model:

```C#
public class PointData
{
    public double XValue { get; set; }
    public double YValue { get; set; }
}
```

2. Define the `ViewModel`:

```C#
public class ScatterViewModel
{
    public ScatterViewModel()
    {
        this.Data = new ObservableCollection<PointData>
        {
            new PointData { XValue = 2, YValue = 13 },
            new PointData { XValue = 5, YValue = 31 },
            new PointData { XValue = 9, YValue = 22 },
            new PointData { XValue = 14, YValue = 45 },
            new PointData { XValue = 22, YValue = 38 },
            new PointData { XValue = 31, YValue = 54 },
        };
    }

    public ObservableCollection<PointData> Data { get; set; }
}
```

3. Define the chart with two `NumericalAxis` instances in XAML:

```XAML
<charts:RadCartesianChart>
    <charts:RadCartesianChart.Axes>
        <charts:CategoricalAxis />
        <charts:NumericalAxis />
    </charts:RadCartesianChart.Axes>
    <charts:RadCartesianChart.Series>
        <charts:LineSeries ItemsSource="{Binding Data}"
                            HorizontalBinding="XValue"
                            VerticalBinding="YValue" />
        <charts:PointSeries ItemsSource="{Binding Data}"
                            HorizontalBinding="XValue"
                            VerticalBinding="YValue"
                            PointSize="10" />
    </charts:RadCartesianChart.Series>
</charts:RadCartesianChart>
```

4. Add the `charts` namespace:

```XAML
xmlns:charts="clr-namespace:Telerik.Maui.Controls.Charts;assembly=Telerik.Maui.Controls"
```

To create a scatter area chart, use `AreaSeries`.
To create a scatter spline area chart, use `SplineAreaSeries`.

## See Also

- [PointSeries]({% slug charts-cartesian-point-series %})
- [LineSeries]({% slug charts-cartesian-line-series %})
- [AreaSeries]({% slug charts-cartesian-area-series %})
- [SplineAreaSeries]({% slug charts-cartesian-spline-area-series %})
- [Numerical Axis]({% slug charts-cartesian-numerical-axis %})
- [Multiple Series]({% slug charts-cartesian-multiple-series %})
