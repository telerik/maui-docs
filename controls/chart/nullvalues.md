---
title: Null Values
page_title: .NET MAUI Chart Documentation - Null Values Support
position: 10
description: Check our &quot;Null Values&quot; documentation article for Telerik Chart for .NET MAUI.
tags: .net maui, ui for .net maui, microsoft, maui
previous_url: /controls/chart/chart-nullvalues
slug: chart-nullvalues
---

# Null Values Support in .NET MAUI Chart

In many scenarios some of the data points that are visualized in the Chart contain empty or null values. These are the cases when data is not available for some records from the used dataset.

In case of Cartesian Series that require X and Y axes (Line, Area, Bar, and so on), the Chart represents `null` data points with an empty space or gap. In case of other chart types (Pie or Donut), these data points are not visualized.

The following example demonstrates a data-bound scenario where a nullable `double` type is used.

1. First, create a `ViewModel` with a collection of `CategoryItems` objects, where a few of the items have null values:

 <snippet id='chart-nullvalues-viewmodel'/>


1. Then, add a `RadCartesianChart` with a Spline Area Series, for example:

 <snippet id='chart-nullvalues-xaml'/>

 1. Add the `telerik` namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
 ```

The image below shows how the null data points are visualized as gaps.

![CartesianChart NullValues](images/chart-nullvalues.png)

## See Also

- [Series Overview]({% slug chart-series-overview %})
