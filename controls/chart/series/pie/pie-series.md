---
title: Pie Series
page_title: .NET MAUI Chart Documentation - Pie Series
slug: chart-series-pie-series
description: Learn more about the Pie series in Telerik UI for .NET MAUI Chart control.
---

# .NET MAUI Chart Pie Series

The Pie Chart visualizes the Pie Series in the shape of a pie. Each data item is visually represented by a pie slice. The ratio between the space consumed by each slice and the space consumed by the whole chart is the same as the ratio between the value of the data point that it represents and the total value of all data points in the series.

## Features

The Pie Series supports the following properties:

- `ValueBinding`&mdash;Defines the binding to a property of the data model that will be used to fill the pie slices.
- `RadiusFactor`&mdash;Defines the radius factor used to calculate the radius of the visual series. This value is usually within the [0,1] range but you can oversize the series by setting a value greater than 1.
- `SelectedPointOffset`&mdash;Defines the offset applied to the currently selected point.

## Example

The following example shows how to create a basic `RadPieChart` with a Pie Series in XAML.

1. Create the needed business object:

 <snippet id='categorical-data-model' />

1. Create a `ViewModel`:

 <snippet id='chart-piechart-view-model' />

1. Declare a `RadPieChart` with Pie Series in XAML:

 <snippet id='chart-piechart-xaml' />


The following image shows the end result:

![Chart PieSeries](images/pie-series-basic-example.png)

## See Also

- [Donut Series]({%slug chart-series-donut-series%})
- [Bar Series]({%slug chart-series-bar-series%})
- [Categorical Series Overview]({%slug chart-series-overview %})
