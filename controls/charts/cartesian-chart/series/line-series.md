---
title: Line Series
page_title: .NET MAUI Cartesian Chart Documentation - Line Series
description: Learn about the LineSeries of the Telerik UI for .NET MAUI Cartesian Chart, its features, configuration, and styling.
components: ["charts"]
tags: charts, cartesian chart, series, line, .net maui
position: 2
slug: charts-cartesian-line-series
---

# .NET MAUI Cartesian Chart Line Series

The `LineSeries` connects the data points with straight line segments.

## Data Binding

The `LineSeries` binds to data through the following properties:

* `ItemsSource` (`IEnumerable`)&mdash;Defines the collection of data items that the series plots.
* `HorizontalBinding` (`string`)&mdash;Defines the name of the data-item member that provides the value of each data point and this value is plotted along the horizontal axis.
* `VerticalBinding` (`string`)&mdash;Defines the name of the data-item member that provides the value of each data point and this value is plotted along the vertical axis.
* `VerticalAxis` (`Telerik.Maui.Controls.Charts.ChartAxis`)&mdash;Defines the vertical axis for the series which values resolved from the `VerticalBinding` property are plotted against.
* `HorizontalAxis` (`Telerik.Maui.Controls.Charts.ChartAxis`)&mdash;Defines the horizontal axis for the series which values resolved from the `HorizontalBinding` property are plotted against.

## Line Customization

Use the following properties to customize the appearance of the line:

* `Stroke` (`Brush`)&mdash;Defines the brush to paint the stroke of the line.
* `StrokeThickness` (`double`)&mdash;Defines the thickness of the line stroke.

## Labels Customization

Use the following properties to configure the labels visualized for each data point:

* `ShowLabels` (`bool`)&mdash;Defines whether the axis labels will be displayed.
* `LabelOffset` (`Size`)&mdash;Defines the offset of the labels from the line.
* `LabelStyle` (`Style` with target type `ChartLabelAppearance`)&mdash;Defines the style of the axis labels.

<snippet id='chart-cartesian-line-series-xaml' />

This is the result:

![.NET MAUI Cartesian Chart LineSeries](../images/charts-cartesian-line-series.png)

> For a runnable example with the Cartesian Chart line series, go to the [SDKBrowser Demo Application]({% slug sdkbrowser-app %}) and navigate to the **Charts > Series** category.

## See Also

- [BarSeries]({% slug charts-cartesian-bar-series %})
- [AreaSeries]({% slug charts-cartesian-area-series %})
- [PointSeries]({% slug charts-cartesian-point-series %})
- [Categorical Axis]({% slug charts-cartesian-categorical-axis %})
