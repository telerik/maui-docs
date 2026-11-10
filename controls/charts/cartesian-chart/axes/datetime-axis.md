---
title: Date-Time Axis
page_title: .NET MAUI Cartesian Chart Documentation - Date-Time Axis
description: Learn how to use the DateTimeAxis in the Telerik UI for .NET MAUI Cartesian Chart to plot data points on a time line and configure its range, step, ticks, label format, and styling.
components: ["charts"]
tags: charts, cartesian chart, axes, datetime, .net maui
position: 3
slug: charts-cartesian-datetime-axis
---

# .NET MAUI Cartesian Chart Date-Time Axis

The `DateTimeAxis` positions the data points on a time line depending on a `System.DateTime` value. Instead of treating each value as an isolated category, the axis builds time slots based on its range and step, which allows it to display empty time slots when no data exists for a given interval.

You define the axis through the `Axes` collection of the `RadCartesianChart`.

## Axis Location

Use the `Location` (enum of type `Telerik.Maui.Controls.Charts.ChartAxisLocation`) property to specify the axis location. The available options are `Left`, `Right`, `Top`, or `Bottom`.

## Line Styling

Use the following properties to customize the appearance of the axis line:

* `LineColor` (`Color`)&mdash;Defines the color of the axis line.
* `LineThickness` (`double`)&mdash;Defines the thickness of the axis line.

## Range and Ticks

Use the following properties to control the time line range, the interval between ticks, and their appearance:

* `Minimum` (`DateTime`)&mdash;Defines the minimum value of the axis range.
* `Maximum` (`DateTime`)&mdash;Defines the maximum value of the axis range.
* `MajorStep` (`double`)&mdash;Defines the interval between adjacent ticks.
* `MajorStepUnit` (`Telerik.Maui.Controls.Charts.ChartTimeInterval`)&mdash;Defines which `DateTime` component the `MajorStep` value refers to: `None`,`Year`, `Quarter`, `Month`, `Week`, `Day`, `Hour`, `Minute`, `Second`, or `Millisecond`. The default value is `None`, so the chart engine choose both the unit and the step automatically based on the axis range and `DesiredTickCount`.
* `WeekStartDay` (`DayOfWeek`)&mdash;Defines the first day of the week when the `MajorStepUnit` is set to `Week`. The default value is `Monday`.
* `DesiredTickCount` (`int`)&mdash;Defines the number of ticks the axis renders.
* `MajorTickColor` (`Color`)&mdash;Defines the color of the major ticks.
* `MajorTickThickness` (`double`)&mdash;Defines the thickness of the major ticks.
* `MajorTickLength` (`double`)&mdash;Defines the length of the major ticks.

## Labels Configuration and Styling

Use the following properties for configuring the axis labels and their appearance:

* `LabelInterval` (`int`)&mdash;Defines the step at which the axis renders labels.
* `LabelFormat` (`string`)&mdash;Defines the format string that is applied to the axis labels, for example `"dd-MM-yy"` or `"HH:mm"`.
* `ShowLabels` (`bool`)&mdash;Defines whether the axis displays labels.
* `LabelStyle` (`Style` with target type `ChartLabelAppearance`)&mdash;Defines the style of the axis labels.
* `LabelFitMode` (`Telerik.Maui.Controls.Charts.ChartAxisLabelFitMode`)&mdash;Defines how the axis arranges its labels. This is a flags enumeration, so you can combine `Rotate` and `Stagger` (for example, `LabelFitMode="Rotate, Stagger"`) to distribute rotated labels across multiple tracks. The available options are:
  * (Default) `None`&mdash;The labels are arranged in a single track without rotation.
  * `Stagger`&mdash;The labels are arranged in outward tracks, leaving at least six device-independent units between the labels in the same track. Staggering moves complete labels and does not wrap their text.
  * `Rotate`&mdash;The labels are rotated by the angle defined by the `LabelRotationAngle` property.
* `LabelRotationAngle` (`double`)&mdash;Defines the angle, in degrees, by which the labels are rotated when `LabelFitMode` includes `Rotate`. Positive values rotate the labels clockwise and negative values rotate them counter-clockwise. The value must be finite. The default value is `-45`.
* `LabelDockPoint` (`Point?`)&mdash;Defines the normalized point of the unrotated label box that is attached to the tick position of the label. Both coordinates must be in the `[0, 1]` range, where `(0, 0)` is the top-left corner and `(1, 1)` is the bottom-right corner of the label. The default value is `null`, which centers the label bounds on the tick along the axis and places them beyond the gap between the tick and the label. An explicit point applies even when the labels are not rotated. Explicitly setting the dock point to the center (`0.5, 0.5`) may extend the label toward the plot area.

## Example

The following example shows how to define a `DateTimeAxis` with a custom step and label format.

1. Define the `DateTimeAxis` as the horizontal axis of the chart.
 
<snippet id='chart-cartesian-datetime-axis-xaml' />

2. Add the `charts` namespace:
 
```XAML
xmlns:charts="clr-namespace:Telerik.Maui.Controls.Charts;assembly=Telerik.Maui.Controls"
```

3. Add the data model:

<snippet id='chart-datamodel-datetime' />

4. Add the `ViewModel`:

<snippet id='chart-datetime-viewmodel' />

This is the result:

![Telerik UI for .NET MAUI CartesianChart with a DateTime axis labeled by months from January through July 2024](../images/charts-cartesian-datetime-axis.png)

> For runnable examples with the Cartesian Chart axes, go to the [SDKBrowser Demo Application]({% slug sdkbrowser-app %}) and navigate to the **Charts > Axes** category.

## See Also

- [Categorical Axis]({% slug charts-cartesian-categorical-axis %})
- [Grid Lines]({% slug charts-cartesian-grid-lines %})
