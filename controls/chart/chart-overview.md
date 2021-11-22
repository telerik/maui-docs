---
title: Overview
page_title: .NET MAUI Chart Documentation | RadChart Overview
description: "Try now the Telerik Chart for .NET MAUI exposing its objects and properties in C#, allowing for no-compromise customization and flexibility."
tags: chart, .net maui, ui for .net maui,
position: 0
slug: chart-overview
---

# Overview

**Telerik UI for .NET MAUI Charts** are feature-rich, intuitive, and easy to use data-visualization controls. While the Chart for .NET MAUI capitalizes all the innate benefits of the native UI, it exposes its objects and properties in C#, allowing for no-compromise customization and flexibility. Using Telerik Chart along with the .NET MAUI allows developers to easily implement various chart scenarios in their applications from a single shared C# code base.

The intuitive object model and public API allow complex charts to be easily set up either in XAML or in code-behind. The Chart is completely data-aware as the binding mechanism of the control is used to create the appropriate data points from the raw data. Chart types and series are organized in hierarchies, depending on the coordinate system, used to plot data points.

![Chart examples](images/chart-overview.png)

## Key Features

Each Telerik UI for .NET MAUI Chart delivers a range of handy and developer-friendly features whose number and further development are not limited by the list in this section. The team constantly invests efforts to improve the performance and add more value to the existing Charts library as well as develop new features and controls to it.

### Behaviors

Each Telerik UI for .NET MAUI Chart can be enabled with interactivity through its `Behaviors` property. A behavior is generally an abstraction that handles user input in a `RadChart` instance and, optionally, provides visual feedback upon some action.

The Telerik UI for .NET MAUI Charts support the following behaviors:

- [`PanAndZoomBehavior`]({% slug chart-behaviors-pan-and-zoom %})&mdash;This behavior handles `Manipulation` events and/or `MouseMove` and `MouseWheel` to enable the panning and zooming of the associated chart plot area.
- [`TooltipBehavior`]({% slug chart-behaviors-tooltip %})&mdash;This behavior handles `Hold` and/or `MouseMove` events to enable context-sensitive information about a data point. It differs from the `TrackballBehavior` in terms of visual information and trigger action.
- [`SelectionBehavior`]({% slug chart-behaviors-selection %})&mdash;This behavior handles the `Tap` event to enable the selection and deselection of data points and/or chart series. When a data point becomes `"Selected"`, you can use the `SelectionPalette` property of the Chart to visualize the selected point.
- [`ChartTrackBallBehavior`]({% slug chart-behaviors-trackball %})&mdash;This behavior handles `Hold` events to enable context-sensitive information about a data point.

### Annotations

You can also show [annotations]({% slug chart-annotations %}) in the Chart. Annotations are visual elements that can be used to highlight certain areas on the plot area and to denote statistical significance.

The provided types of annotations include:

- `CartesianGridLine`&mdash;In the Cartesian Chart, the grid line represents a vertical or horizontal line which crosses the entire plot area.
- `CartesianPlotBand`&mdash;The Cartesian Plot Band annotation is either a horizontal or a vertical stripe that crosses entirely the vertical or horizontal axis respectively.

### Labels

The Chart can display different labels for the series and axes that are displayed. Additionally, you can customize the labels according to your preferences.

## Available Chart Types

The Telerik UI for .NET MAUI Chart provides a number of series, which enable you to visualize different types of data in various ways and depending on your preferences and requirements.

### Cartesian Charts

The [Cartesian Chart]({% slug chart-types-cartesian-chart %}) control uses the Cartesian coordinate system to plot the data points in its chart series. The X and Y axes define how the coordinates of each point in the plot area are calculated.

#### Axes

The following Cartesian axes are available:

- [Categorical axis]({% slug axes-categorical-axis %})&mdash;Arranges the plotted data points in categories where the key of each category is the point’s value (if available) for that axis or its index within the points collection. The coordinate of the point, specified by this axis, is discrete and is calculated depending on the size of the category slot where the point resides.
- [Numerical axis]({% slug axes-numerical-axis %})&mdash;Calculates the coordinate of each data point, depending on the actual numerical value this point provides for the axis. Exposes the `Minimum` and `Maximum` properties to allow you to explicitly define the range of values visible on this axis. If these properties are not specified, the axis will automatically calculate the range depending on the minimum and maximum data point values.
- [Date-Time Continuous axis]({% slug axes-date-time-continuous-axis %})&mdash;A special axis that expects each data point to provide a `System.DateTime` structure as its value for this axis. Think of this axis as a time line where the coordinate of each data point is calculated depending on the position of its associated date and time on the time line. The base unit (or the step) of the axis is calculated depending on the smallest difference between any two dates.

#### Series

The Cartesian Chart supports the Categorical and Scatter series:

  * Categorical Cartesian Chart series&mdash;Need a [Numerical]({% slug axes-numerical-axis %}) and a [Categorical]({% slug axes-categorical-axis %}) or [Date-Time Continuous]({% slug axes-date-time-continuous-axis %}) axes to get properly plotted.

  The Categorical Cartesian Chart supports the following series:

  - [Bar]({% slug chart-series-bar-series %})&mdash;Data points are represented by a box where the height (width) of the box is the distance between the numerical value of the point and the categorical axis that plots the point. Bars may be either horizontal or vertical depending on whether the categorical axis is specified as an `"X-axis"` or as a `"Y-axis"`.
  - [Line]({% slug chart-series-line-series %})&mdash;Data points are connected with straight line segments.
  - [Spline]({% slug chart-series-spline-series %})&mdash;Data points are connected with smooth line segments.
  - [Area]({% slug chart-series-area-series %})&mdash;Data points and the corresponding coordinate axis enclose an area that may be optionally stroked and/or filled.
  - [SplineArea]({% slug chart-series-spline-area-series %})&mdash;An area where points are connected with smooth rather than straight segments.

  You can combine each of the above series of the same type in [stacks or clusters]({% slug chart-series-combine-mode %}). Combinations are formed when more than one data point from different series fall within the same category. The Cluster combine mode will position such points next to each other while the Stack combine mode will arrange such points in a stack-like structure. When stacks are formed, the numerical axis (if present) will consider each stack as a single entity and its sum will be the actual used value rather than the value of each point.

- Scatter Cartesian Chart series&mdash;Scatter series require two Numerical axes to get properly plotted. Scattered data provides both the X and the Y coordinate.

  The Scatter Cartesian Chart supports the following series:

  - [ScatterPoint]({% slug chart-series-scatter-point-series %})&mdash;Data points are represented by an arbitrary template.
  - [ScatterLine]({% slug chart-series-scatter-line-series %})&mdash;Data points are connected with straight line segments.
  - [ScatterSpline]({% slug chart-series-scatter-spline-series %})&mdash;Data points are connected with smooth line segments.
  - [ScatterArea]({% slug chart-series-scatter-area-series %})&mdash;Data points and the horizontal axis enclose an area that may be optionally stroked and/or filled.
  - [ScatterSplineArea]({% slug chart-series-scatter-spline-area-series %})&mdash;A ScatterArea Chart where points are connected with smooth rather than straight segments.

### Cartesian Chart Grid

The [Chart Grid type]({% slug cartesian-chart-grid %}) is a Cartesian Chart that is optionally decorated with grid-like visuals, which support horizontal and vertical lines, and are associated with axis ticks and horizontal and vertical stripes (the area between two adjacent ticks).

### Pie Chart

The [Pie Chart type]({% slug chart-types-pie-chart %}) visualizes its data points by using a discrete polar coordinate system. Each point is represented as an arc segment. The arc length represents the point’s value percentage of the total sum.

## Next Steps

- [Getting Started with Telerik UI for .NET MAUI Charts]({% slug barcode-getting-started %})
