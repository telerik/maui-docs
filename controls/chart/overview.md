---
title: Overview
page_title: .NET MAUI Chart Documentation - Overview
description: Try now the Telerik Chart for .NET MAUI exposing its objects and properties in C#, allowing for no-compromise customization and flexibility.
tags: chart, .net maui, ui for .net maui, chart, barseries
position: 0
previous_url: /controls/chart/chart-overview
slug: chart-overview
---

# .NET MAUI Chart Overview

The Telerik UI for .NET MAUI Charts are feature-rich, intuitive, and easy-to-use data-visualization controls. While the Chart for .NET MAUI capitalizes on all the innate benefits of the native UI, it exposes its objects and properties in C#, allowing for no-compromise customization and flexibility. Using the Telerik Chart along with .NET MAUI allows developers to implement various chart scenarios in their applications from a single shared C# code base.

The intuitive object model and public API allow complex charts to be set up either in XAML or in code-behind. The Chart is data-aware as the binding mechanism of the control is used to create the data points from the raw data. Chart types and series are organized in hierarchies, depending on the coordinate system, used to plot data points.

![.NET MAUI Chart Overview](images/chart-overview.png)

## Chart Types

The Telerik UI for .NET MAUI Chart provides the Cartesian and the Pie Charts as well as a number of series, which enable you to visualize different types of data in various ways and depending on your preferences and requirements.

### Cartesian Charts

The [Cartesian Chart]({% slug chart-types-cartesian-chart %}) uses the Cartesian coordinate system to plot the data points in its chart series. The X and Y axes define how the coordinates of each point in the plot area are calculated.

The following series are part of the CartesianChart:

* Categorical Series such as the [Area Series]({% slug chart-series-area-series %}), [Bar Series]({% slug chart-series-bar-series %}), and [Line Series]({%slug chart-series-line-series%}).
* Scatter Series such as the [ScatterLine Series]({% slug chart-series-scatter-line-series %}) and [ScatterPoint Series]({% slug chart-series-scatter-point-series %}).
* Financial Series such as the [OHLC Series]({% slug chart-series-ohlc-series %}) and [Candlestick Series]({% slug chart-series-candlestick-series %}).

#### Chart Axes

Depending on the type of Cartesian Chart and the used series, the Chart provides:
* a [Categorical axis]({% slug axes-categorical-axis %}).
* a [Numerical axis]({% slug axes-numerical-axis %}).
* a [Date-Time Continuous axis]({% slug axes-date-time-continuous-axis %}).

#### Chart Grid

The [Chart Grid type]({% slug cartesian-chart-grid %}) is optionally decorated with grid-like visuals, which support horizontal and vertical lines, and are associated with axis ticks and horizontal and vertical stripes (the area between two adjacent ticks).

### Pie Charts

The [Pie Chart]({% slug chart-types-pie-chart %}) visualizes its data points by using a discrete polar coordinate system. Each point is represented as an arc segment. The arc length represents the point’s value percentage of the total sum. The following series are part of the `PieChart`:

* [Donut Series]({% slug chart-series-donut-series %})
* [Pie Series]({% slug chart-series-pie-series %})

## Key Features of the .NET MAUI Chart

Each Telerik UI for .NET MAUI Chart delivers a range of handy and developer-friendly features whose number and further development are not limited by the list in this section. The team constantly invests efforts to improve the performance and add more value to the existing Charts library as well as develop new features and controls to it.

### Behaviors

Each Telerik UI for .NET MAUI Chart can be enabled with interactivity through its `Behaviors` property. The behavior functionality is an abstraction that handles user input in a `RadChart` instance and, optionally, provides visual feedback upon some action.

The Telerik UI for .NET MAUI Charts support the following behaviors:

- [Pan-and-Zoom behavior]({% slug chart-behaviors-pan-and-zoom %})&mdash;This behavior handles `Manipulation` events and/or `MouseMove` and `MouseWheel` to enable the panning and zooming of the associated chart plot area.
- [Tooltip behavior]({% slug chart-behaviors-tooltip %})&mdash;This behavior handles the `Hold` and/or `MouseMove` events to enable context-sensitive information about a data point. The Tooltip behavior differs from the `TrackballBehavior` in its visual information and trigger action.
- [Selection behavior]({% slug chart-behaviors-selection %})&mdash;This behavior handles the `Tap` event to enable the selection and deselection of data points and/or chart series. When a data point becomes selected, you can use the `SelectionPalette` property of the Chart to visualize the selected point.
- [TrackBall behavior]({% slug chart-behaviors-trackball %})&mdash;This behavior handles `Hold` events to enable context-sensitive information about a data point.

### Annotations

You can also show [annotations]({% slug chart-annotations%}) in the Chart. Annotations are visual elements that can be used to highlight some areas on the plot area and to denote statistical significance.

The provided types of annotations include:

- `CartesianGridLine`&mdash;In the Cartesian Chart, the grid line represents a vertical or horizontal line which crosses the entire plot area.
- `CartesianPlotBand`&mdash;The Cartesian Plot Band annotation is either a horizontal or a vertical stripe that crosses entirely the vertical or horizontal axis respectively.

### Labels

The Chart can display different labels for the series and axes that are displayed. Additionally, you can customize the labels according to your preferences.

### Legend

The [Legend feature]({%slug chart-features-legend%}) of the `RadChart` provides description about the series which are visualized within the control.

### Null Values support

The Chart represents null data points with an empty space or gap. For more details on this feature, review the [Null Values Support]({%slug chart-nullvalues%}) article.

## Next Steps

- [Getting Started with Telerik UI for .NET MAUI Charts]({% slug chart-getting-started %})
- [Overview of the Cartesian Charts]({% slug chart-types-cartesian-chart %})
- [Overview of the Pie Charts]({% slug chart-types-pie-chart %})
- [Overview of the Chart Series]({% slug chart-series-overview %})
- [Common Features for the Chart Series]({% slug chart-series-features %})

## See Also

- [.NET MAUI Chart Product Page](https://www.telerik.com/maui-ui/chart)
- [.NET MAUI Chart Forum Page](https://www.telerik.com/forums/maui?tagId=1765)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
