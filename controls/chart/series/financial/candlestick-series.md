---
title: Candlestick Series
page_title: .NET MAUI Chart Documentation - Candlestick Series
slug: chart-series-candlestick-series
description: Learn more about the Candlestick series in the Telerik UI for .NET MAUI Chart control. 
position: 1
---

# .NET MAUI Chart Candlestick Series

The Cartesian Chart visualizes each data point from the Candlestick Series as a visual that resembles a candlestick. This is a typical financial series that can be used to visualize the state of a market for a period of time. The series operates with a special data in the form of four parameters defining the stock market - **open**, **high**, **low**, and **close**. The **high** and **low** values show the price range (the highest and lowest prices) over one unit of time. The **open** and **close** values indicate the opening and closing price of the stock for the corresponding period

## Example

The following example shows how to create a basic `RadCartesianChart` with a Candlestick Series in XAML and C#.

**1.** Define the `RadCartesianChart`.

<snippet id='chart-series-candlestick-xaml' />

**2.** Define the business model:

<snippet id='chart-ohlc-datapoint-csharp' />

**3.** And the ViewModel:

<snippet id='chart-financial-indicator-viewmodel' />

The following image shows the end result:

![Chart Candlestick](images/candlestick_series.png)

## See Also

- [Ohlc Series Overview]({%slug chart-series-ohlc-series%})
- [Financial Indicators]({%slug chart-series-financial-indicators%})
