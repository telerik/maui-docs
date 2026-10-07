---
title: Null Values
page_title: .NET MAUI CartesianChart Documentation - Null Values
description: Learn how to handle null values in the Telerik UI for .NET MAUI Cartesian Chart series.
components: ["charts"]
tags: charts, cartesian chart, null values, .net maui, ui for .net maui
position: 8
slug: charts-cartesian-null-values
---

# .NET MAUI Cartesian Chart Null Values

In many scenarios some of the data points that are visualized in the Chart contain empty or null values. These are the cases when data is not available for some records from the used dataset.

The Telerik UI for .NET MAUI CartesianChart series support null values and when a data point is null, the series will skip it and continue to the next available data point. The series will not render a point for the null value, the data point will be rendered as an empty space or gap.

## Example

The following example demonstrates how to handle null values in a `SplineAreaSeries`.

1. Define the Chart with `SplineAreaSeries`:

<snippet id='chart-cartesian-null-values-xaml' />

2. Add the `charts` namespace:

```XAML
xmlns:charts="clr-namespace:Telerik.Maui.Controls.Charts;assembly=Telerik.Maui.Controls"
```

3. Define the data model and `ViewModel`:

<snippet id='chart-null-values-viewmodel' />

This is the result:

![Telerik UI for .NET MAUI CartesianChart with null values](images/charts-cartesian-null-values.png)

> For a runnable example with the CartesianChart null values scenario, go to the [SDKBrowser Demo Application]({% slug sdkbrowser-app %}) and navigate to the **Charts > Features** category.

## See Also

- [Chart Plot Areas]({% slug charts-cartesian-plot-areas %})
- [AreaSeries]({% slug charts-cartesian-area-series %})
- [PointSeries]({% slug charts-cartesian-point-series %})
- [Categorical Axis]({% slug charts-cartesian-categorical-axis %})