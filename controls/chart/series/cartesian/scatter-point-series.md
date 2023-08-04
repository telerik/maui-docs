---
title: ScatterPoint Series
page_title: .NET MAUI Chart Documentation - ScatterPoint Series
description: Learn more about the ScatterPoint series in the Cartesian chart.
slug: chart-series-scatter-point-series
position: 0
---

# .NET MAUI Chart ScatterPoint Series

The ScatterPoint Series are represented on the chart as data points that are not connected. Each scatter data point has to provide values for the X and Y coordinates on the `RadCartesianChart`. The ScatterPoint Series require both axes of the chart to be Numerical Axes.

## Features

The ScatterPoint Series provides the following properties:

- `XValueBinding`&mdash;Defines the binding that will be used to fill the `XValue` of the `ScatterDataPoint` members of the `DataPoints` collection.
- `YValueBinding`&mdash;Defines the binding that will be used to fill the `YValue` of the `ScatterDataPoint` members of the `DataPoints` collection.

## Example

The following example shows how to create a `RadCartesianChart` with a ScatterPoint Series:

1. Create the needed business objects, for example:

 <snippet id='numerical-data-model' />


1. Create a `ViewModel`:

 <snippet id='chart-series-series-numerical-view-model' />


1. Use the following snippet to declare a `RadCartesianChart` with a ScatterPoint Series in XAML and in C#:

 <snippet id='chart-series-scatterpoint-xaml' />



The following image shows the end result:

![Basic ScatterPointSeries](images/cartesian-scatter-point-series-basic-example.png)

## See Also

- [Line Series]({%slug chart-series-line-series%})
- [ScatterLine Series]({%slug chart-series-scatter-line-series%})
- [Spline Series]({%slug chart-series-spline-series%})
