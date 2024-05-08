---
title: Pie Series
page_title: .NET MAUI Chart Documentation - Pie Series
slug: chart-series-pie-series
description: Learn more about the Pie series in the Telerik UI for .NET MAUI Chart control.
---

# .NET MAUI Chart Pie Series

The Pie Chart visualizes the Pie Series in the shape of a pie. Each data item is visually represented by a pie slice. The ratio between the space consumed by each slice and the space consumed by the whole chart is the same as the ratio between the value of the data point that it represents and the total value of all data points in the series.

## Features

The Pie Series supports the following properties:

- `ValueBinding`&mdash;Defines the binding to a property of the data model that will be used to fill the pie slices.
- `RadiusFactor`&mdash;Defines the radius factor used to calculate the radius of the visual series. This value is usually within the [`0,1`] range but you can oversize the series by setting a value greater than `1`.
- `SelectedPointOffset`&mdash;Defines the offset applied to the currently selected point.

## Example

The following example shows how to create a basic `RadPieChart` with a Pie Series in XAML.

**1.** Create the business object:

<snippet id='categorical-data-model' />

**2.** Define a sample `ViewModel`:

<snippet id='chart-piechart-view-model' />

**3.** Declare a `RadPieChart` with Pie Series in XAML:

<snippet id='chart-piechart-xaml' />

The following image shows the end result:

![Chart PieSeries](images/pie-series-basic-example.png)

## Label Customization

If you want to customize the labels in the pie series (setting color, formatting the value, changing the font family and so on) you have to use the native Android, iOS and WinUI chart control. 

For more details what are the steps for customizing the labels, review the [Customizing Labels in the Pie Chart]({%slug piechart-label-customization%}) artcile.

## See Also

- [Donut Series]({%slug chart-series-donut-series%})
- [Bar Series]({%slug chart-series-bar-series%})
- [Categorical Series Overview]({%slug chart-series-overview %})
