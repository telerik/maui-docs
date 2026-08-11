---
title: Bar Series
page_title: .NET MAUI Cartesian Chart Documentation - BarSeries
description: Learn about the BarSeries of the Telerik UI for .NET MAUI Cartesian Chart, its features, configuration, and styling.
tags: charts, cartesian chart, series, bar, .net maui
position: 1
slug: charts-cartesian-bar-series
---

# .NET MAUI Cartesian Chart Bar Series

The `BarSeries` is used to visualize data in a categorical chart, where each bar represents a category and its value. The bars can be displayed vertically or horizontally, depending on the chart's orientation.

## Data Binding

The `BarSeries` binds to data through the following properties:

* `ItemsSource` (`IEnumerable`)&mdash;Defines the collection of data items that the series plots.
* `HorizontalBinding` (`string`)&mdash;Defines the name of the data-item member that provides the value of each bar and this value is plotted along the horizontal axis.
* `VerticalBinding` (`string`)&mdash;Defines the name of the data-item member that provides the value of each bar and this value is plotted along the vertical axis.
* `VerticalAxis` (`Telerik.Maui.Controls.Charts.ChartAxis`)&mdash;Defines the vertical axis for the series which values resolved from the `VerticalBinding` property are plotted against.
* `HorizontalAxis` (`Telerik.Maui.Controls.Charts.ChartAxis`)&mdash;Defines the horizontal axis for the series which values resolved from the `HorizontalBinding` property are plotted against.

## Bars Customization

Use the following properties to customize the appearance of the bars:

* `Fill` (`Brush`)&mdash;Defines the fill of the bars.
* `Stroke` (`Brush`)&mdash;Defines the brush to paint the stroke of the bars.
* `StrokeThickness` (`double`)&mdash;Defines the thickness of the bar stroke.
* `CornerRadius` (`double`)&mdash;Defines the corner radius of the bars. The default value is `0`, which means that the bars will have sharp corners. Set a positive value to round the corners of the bars.
* `CombineMode` (enum of type `Telerik.Maui.Controls.Charts.BarCombineMode`)&mdash;Defines how the bars are combined when multiple series are plotted in the same chart. The available options are `Clustered`, `Stacked`, and `Stack100`. The default value is `Clustered`.

## Labels Customization

Use the following properties to configure the labels visualized for each data point:

* `ShowLabels` (`bool`)&mdash;Defines whether the axis labels will be displayed.
* `LabelOffset` (`Size`)&mdash;Defines the offset of the labels from the bars.
* `LabelStyle` (`Style` with target type `ChartLabelAppearance`)&mdash;Defines the style of the axis labels.

<snippet id='chart-cartesian-bar-series-xaml' />

This is the result:

![.NET MAUI Cartesian Chart BarSeries](../images/charts-cartesian-bar-series.png)

> For a runnable example with the Cartesian Chart bar series, go to the [SDKBrowser Demo Application]({% slug sdkbrowser-app %}) and navigate to the **Charts > Series** category.

## See Also

- [Series Overview]({% slug charts-cartesian-series %})
- [LineSeries]({% slug charts-cartesian-line-series %})
- [AreaSeries]({% slug charts-cartesian-area-series %})
- [PointSeries]({% slug charts-cartesian-point-series %})
- [Categorical Axis]({% slug charts-cartesian-categorical-axis %})
