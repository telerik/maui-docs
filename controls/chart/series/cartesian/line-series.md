---
title: Line Series
page_title: .NET MAUI Chart Documentation - Line Series
description: Learn more about Line series that Telerik UI for .NET MAUI Chart control visualize.
position: 0
slug: chart-series-line-series
---

# .NET MAUI Chart Line Series

The Cartesian Chart visualizes each data item from the Line Series and connects them with straight line segments. The Line Series extend the Categorical Stroked Series, so they are also Categorical Series and require one Categorical Axis and one Numerical Axis.

## Features

The Line Series supports the following properties:

- `Stroke` (Color)&mdash;Changes the color for drawing lines.
- `StrokeThickness` (double)&mdash;Changes the width of the lines.

## Line Series Example

The following example shows how to create a `RadCartesianChart` with a Line Series:

1. Create the needed business objects, for example:

 <snippet id='categorical-data-model' />


1. Create a `ViewModel`:

 <snippet id='chart-series-series-categorical-view-model' />


1. Finally, use the following snippet to declare a `RadCartesianChart` with a Line Series in XAML:

 <snippet id='chart-series-line-xaml' />



The following image shows the end result:

![Basic LineSeries](images/cartesian-line-series-basic-example.png)

## Customization Example

You can further customize the Line Series:

```C#
	var series = new LineSeries
	{
		Stroke = new Color(0.6, 0.6, 0.9),
		StrokeThickness = 5
	};
```

![Customized LineSeries](images/cartesian-line-series-customization-example.png)

## See Also

- [ScatterArea Series]({%slug chart-series-scatter-area-series%})
- [ScatterLine Series]({%slug chart-series-scatter-line-series%})
- [ScatterPoint Series]({%slug chart-series-scatter-point-series%})
