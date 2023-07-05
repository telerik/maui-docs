---
title: Series Overview
page_title: .NET MAUI Chart Documentation - Series Overview
description: Try now the Telerik RadChart for .NET MAUI
slug: chart-series-overview
previous_url: /controls/chart/series/chart-series-overview
position: 0
---

# .NET MAUI Chart Series

The data visualization in the Chart is done by a hierarchy of classes that inherit from the `ChartSeries` class. Each series has a collection of data points, that is the view model of the data. A series may have its data populated by data-binding to an arbitrary `IEnumerable` instance through the `ItemsSource` property.

## Series Class Hierarchy

Specific series types are available for specific charts. For example, a set of Cartesian Series is applicable in the context of a `RadCartesianChart`.

The following image shows the hierarchy of all series:

![Chart Series Class Diagram](images/chart-series-class-diagram.png)

## Cartesian Chart Series

The Cartesian Chart provides a number of Categorical and Scatter Series.

- Supported Categorical Series:

    - [Bar Series]({%slug chart-series-bar-series %})
    - [Line Series]({%slug chart-series-line-series %})
    - [Spline Series]({%slug chart-series-spline-series %})
    - [Area Series]({%slug chart-series-area-series %})
    - [SplineArea Series]({%slug chart-series-spline-area-series %})

- Supported Scatter Series:

    - [ScatterPoint Series]({% slug chart-series-scatter-point-series%})
    - [ScatterLine Series]({% slug chart-series-scatter-line-series%})
    - [ScatterSpline Series]({% slug chart-series-scatter-spline-series%})
    - [ScatterArea Series]({% slug chart-series-scatter-area-series%})
    - [ScatterSplineArea Series]({% slug chart-series-scatter-spline-area-series%})

## Pie Chart Series

The Pie Chart provides the following series:

- [Pie Series]({%slug chart-series-pie-series%})
- [Donut Series]({%slug chart-series-donut-series%})

## Financial Chart Series

The Financial Chart provides the following series:

- [OHLC Series]({%slug chart-series-ohlc-series%})
- [Candlestick Series]({%slug chart-series-candlestick-series%})
- [Financial Series]({%slug chart-series-financial-indicators%})

## See Also

- [Annotations]({%slug chart-annotations%})
- [Chart Legend]({%slug chart-features-legend%})
- [Null Values]({%slug chart-nullvalues%})
