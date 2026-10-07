---
title: Spline Series
page_title: .NET MAUI Cartesian Chart Documentation - Spline Series
description: Learn about the SplineSeries of the Telerik UI for .NET MAUI Cartesian Chart, its features, configuration, and styling.
components: ["charts"]
tags: charts, cartesian chart, series, spline, .net maui
position: 3
slug: charts-cartesian-spline-series
---

# .NET MAUI Cartesian Chart Spline Series

The `SplineSeries` represents a series of data points connected by a smooth curve.

## Data Binding

The `SplineSeries` binds to data through the following properties:

* `ItemsSource` (`IEnumerable`)&mdash;Defines the collection of data items that the series plots.
* `HorizontalBinding` (`string`)&mdash;Defines the name of the data-item member that provides the value of each data point and this value is plotted along the horizontal axis.
* `VerticalBinding` (`string`)&mdash;Defines the name of the data-item member that provides the value of each data point and this value is plotted along the vertical axis.
* `VerticalAxis` (`Telerik.Maui.Controls.Charts.ChartAxis`)&mdash;Defines the vertical axis for the series which values resolved from the `VerticalBinding` property are plotted against.
* `HorizontalAxis` (`Telerik.Maui.Controls.Charts.ChartAxis`)&mdash;Defines the horizontal axis for the series which values resolved from the `HorizontalBinding` property are plotted against.

## Spline Customization

Use the following properties to customize the appearance of the spline:

* `Stroke` (`Brush`)&mdash;Defines the brush to paint the stroke of the spline.
* `StrokeThickness` (`double`)&mdash;Defines the thickness of the spline stroke.

## Labels Customization

Use the following properties to configure the labels visualized for each data point:

* `ShowLabels` (`bool`)&mdash;Defines whether the axis labels will be displayed.
* `LabelOffset` (`Size`)&mdash;Defines the offset of the labels from the spline.
* `LabelStyle` (`Style` with target type `ChartLabelAppearance`)&mdash;Defines the style of the axis labels.

## Example

The following example shows how to define a `SplineSeries`.

1. Define the `SplineSeries` and the chart definition in XAML:

<snippet id='chart-cartesian-spline-series-xaml' />

2. Add the `charts` namespace:
 
```XAML
xmlns:charts="clr-namespace:Telerik.Maui.Controls.Charts;assembly=Telerik.Maui.Controls"
```

3. Add the data model:

<snippet id='chart-datamodel-categorical-data' />

4. Add the `ViewModel`:

<snippet id='chart-categorical-viewmodel' />

This is the result:

![Telerik UI for .NET MAUI CartesianChart SplineSeries with a red filled area across monthly categories](../images/charts-cartesian-spline-series.png)

> For a runnable example with the Cartesian Chart spline series, go to the [SDKBrowser Demo Application]({% slug sdkbrowser-app %}) and navigate to the **Charts > Series** category.

## See Also

- [BarSeries]({% slug charts-cartesian-bar-series %})
- [LineSeries]({% slug charts-cartesian-line-series %})
- [PointSeries]({% slug charts-cartesian-point-series %})
- [Categorical Axis]({% slug charts-cartesian-categorical-axis %})
