---
title: SplineArea Series
page_title: .NET MAUI Chart Documentation - SplineArea Series
description: Check our &quot;SplineArea Series&quot; documentation article for Telerik Chart for .NET MAUI
slug: chart-series-spline-area-series
position: 0
---

# SplineArea Series

The Cartesian Chart visualizes the SplineArea Series as an area on the chart that is enclosed by the coordinate axes and straight line segments, which connect the data points represented by these series. The SplineArea Series extend the Categorical Stroked Series, so they are also Categorical Series and require one Categorical Axis and one Numerical Axis.

## Features

The SplineArea Series provides the following properties:

- `Stroke` (Color)&mdash;Changes the color for drawing lines.
- `StrokeThickness` (double)&mdash;Changes the width of the lines.
- `Fill` (Color)&mdash;Changes the color for filling the area shapes.

## SplineArea Series Example

The following example shows how to create a `RadCartesianChart` with a SplineArea Series:

1. First, create the needed business objects, for example:

 <snippet id='categorical-data-model' />


1. Then, create a `ViewModel`:

 <snippet id='chart-series-categorical-view-model' />


1. Finally, use the following snippet to declare a `RadCartesianChart` with a SplineArea Series in XAML and in C#:

 <snippet id='chart-series-splinearea-xaml' />


The following image shows the end result:

![Basic SplineAreaSeries](images/cartesian-spline-area-series-basic-example.png)

## Customization Example

You can further customize the SplineArea Series:

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
