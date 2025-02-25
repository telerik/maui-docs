---
title: Pie Chart
page_title: .NET MAUI Chart Documentation - Pie Chart
position: 2
description: Learn how to configure the Telerik UI for .NET MAUI PieChart control.
previous_url: /controls/chart/types/chart-types-pie-chart
slug: chart-types-pie-chart
---

# .NET MAUI Pie Chart

The Pie Chart visualizes its data points by using the radial coordinate system. Each data point is represented as a slice from a pie. The ratio between the space consumed by each slice and the space consumed by the whole chart is the same as the ratio between the value of the data point that it represents and the total value of all data points in the series.

## Properties

The Pie Chart supports the following properties:

* `Series`&mdash;Gets a collection of all series presented by the chart instance.
* `Behaviors`&mdash;Gets a collection of all enabled behaviors.
* `Palette`&mdash;Gets or sets the `ChartPalette` instance that defines the appearance of the chart.
* `PaletteName`&mdash;Gets or sets the name of the predefined `Palette` that will be applied to the chart.
* `SelectionPalette`&mdash;Gets or sets the `ChartPalette` instance that defines the appearance of the chart for the selected series and/or data points.
* `SelectionPaletteName`&mdash;Gets or sets the name of the predefined `SelectionPalette` that will be applied to the chart.

## Series

The PieChart supports the Pie Series, which visualize a single series of data in a pie chart. The sweep of a pie slice is directly proportional to the magnitude of the data point values.

## Customize the Chart Colors

You can take advantage of the available customization options the Chart control provides. You can change the default Chart and series colors by setting a `Palette`. For more details on the suggested implementation, see the [Creating Custom PieChart Palettes KB article]({%slug pie-chart-custom-colors%}).

## PieChart Example

The following example shows the full definition of the chart.

**1.** Create the needed business object, for example:

<snippet id='categorical-data-model' />

**2.** Create a `ViewModel`:

<snippet id='chart-piechart-view-model' />

**3.** Declare a `RadPieChart` with a Pie Series in XAML:

<snippet id='chart-piechart-xaml' />

The following image shows the end result:

![Pie Chart](images/pie-chart-example.png)

## See Also

- [Cartesian Chart]({%slug chart-types-cartesian-chart%})
- [Chart Legend]({%slug chart-features-legend%})
- [Chart Null Values]({%slug chart-nullvalues%})
