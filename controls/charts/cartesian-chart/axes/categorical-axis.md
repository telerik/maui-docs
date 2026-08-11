---
title: Categorical Axis
page_title: .NET MAUI Cartesian Chart Documentation - Categorical Axis
description: Learn how to use the CategoricalAxis in the Telerik UI for .NET MAUI Cartesian Chart to arrange data points into discrete categories and configure its labels, ticks, and styling.
components: ["charts"]
tags: charts, cartesian chart, axes, categorical, .net maui
position: 1
slug: charts-cartesian-categorical-axis
---

# .NET MAUI Cartesian Chart Categorical Axis

The `CategoricalAxis` arranges the data points in categories. The axis is divided into discrete slots and each data point is visualized in the slot that corresponds to its categorical value. Use a `CategoricalAxis` when one of the chart dimensions represents categories rather than numeric or date-time values&mdash;for example, when plotting a `BarSeries` against a `NumericalAxis`.

You define the axis through the `HorizontalAxis`, the `VerticalAxis`, or the `Axes` collection of the `RadCartesianChart`.

## Axis Location

Use the `Location` (enum of type `Telerik.Maui.Controls.Charts.ChartAxisLocation`) property to specify the axis location. The available options are `Left`, `Right`, `Top`, or `Bottom`.

Use the `GapLength` (`double`) property to specify the distance between the axis and the chart area.  The value is in the `[0, 1]` range, defaults to `0.3`.

## Line Styling

Use the following properties to customize the appearance of the axis line:

* `LineColor` (`Color`)&mdash;Defines the color of the axis line.
* `LineThickness` (`double`)&mdash;Defines the thickness of the axis line.

## Labels Customization

The Categorical Axis exposes the following properties for configuring its position, labels, and appearance:

* `ShowLabels` (`bool`)&mdash;Defines whether the axis labels will be displayed.
* `LabelStyle` (`Style` with target type `ChartLabelAppearance`)&mdash;Defines the style of the axis labels.
* `LabelInterval` (`int`)&mdash;Defines the step at which the axis renders labels.
* `CategoryLabelFormat` (`string`)&mdash;Defines the format of the axis labels. 

## Example

The following example shows how to configure a `CategoricalAxis` as the horizontal axis of the chart.

```XAML
<telerik:RadCartesianChart.HorizontalAxis>
    <telerik:CategoricalAxis LabelInterval="2" />
</telerik:RadCartesianChart.HorizontalAxis>
```

> For runnable examples with the Cartesian Chart axes, go to the [SDKBrowser Demo Application]({% slug sdkbrowser-app %}) and navigate to the **Chart > Axes** category.

## See Also

- [Numerical Axis]({% slug charts-cartesian-numerical-axis %})
- [Grid Lines]({% slug charts-cartesian-grid-lines %})
