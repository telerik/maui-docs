---
title: Area Series
page_title: .NET MAUI Chart Area Series Documentation
description: Learn how to use the Telerik UI for .NET MAUI Chart Area Series, bind categorical data, customize its fill and stroke, and style the chart.
components: ["chart"]
slug: chart-series-area-series
position: 0
---

# .NET MAUI Chart Area Series

Use `AreaSeries` to plot categorical data as a continuous line with a filled area between the line and the chart axis. This series is useful when you want to emphasize both the trend and the magnitude of the values across categories.

`AreaSeries` derives from the categorical stroked series types, so it requires one categorical axis and one numerical axis in a `RadCartesianChart`. The axes define the coordinates and the boundary of the filled area, while the `Fill` property defines its color.

## When to Use the Area Series

Use `AreaSeries` when you want to:

- Show how values change across categories.
- Emphasize the distance between the data points and the chart baseline.
- Combine a trend line with a filled visual that is easier to compare at a glance.

## Features

The `AreaSeries` exposes the following properties:

- `Fill` (`Color`)&mdash;Defines the fill of the area.
- `Stroke` (`Color`)&mdash;Defines the color of the series line.
- `StrokeThickness` (`double`)&mdash;Defines the width of the series line.

## Area Series Example

The following example shows how to create a `RadCartesianChart` with an `AreaSeries`:

1. Create a sample business object:

<snippet id='categorical-data-model' />

2. Create a `ViewModel`:

<snippet id='chart-series-categorical-view-model' />

3. Declare a `RadCartesianChart` with an `AreaSeries` in XAML or C#:

<snippet id='chart-series-area-xaml' />

The following image shows the result:

![Telerik UI for .NET MAUI Cartesian Chart AreaSeries with a light blue region shaded below the line](images/cartesian-area-series-basic-example.png)

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

The following image shows a customized area series with a thicker line and a light fill:

![Telerik UI for .NET MAUI Cartesian Chart customized AreaSeries with a thicker purple stroke and light purple fill](images/cartesian-area-series-customization-example.png)

## See Also

- [Chart Axes Overview]({%slug axes-overview%})
- [Categorical Axis]({%slug axes-categorical-axis%})
- [Bar Series]({%slug chart-series-bar-series%})
- [Line Series]({%slug chart-series-line-series%})
- [Spline Series]({%slug chart-series-spline-series%})
- [Spline Area Series]({%slug chart-series-spline-area-series%})
- [Scatter Area Series]({%slug chart-series-scatter-area-series%})
- [Scatter Spline Area Series]({%slug chart-series-scatter-spline-area-series%})
