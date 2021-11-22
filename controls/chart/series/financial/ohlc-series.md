---
title: OHLC
page_title: .NET MAUI Chart Documentation | OHLC Series
slug: chart-series-ohlc-series
description: Check our &quot;Ohlc Series&quot; documentation article for Telerik Chart for .NET MAUI
position: 0
---

# OHLC Series

The Cartesian Chart visualizes each data point from the OHLC Series as a line with open and close value indicators on its side. This is a typical financial series that can be used to visualize the state of a market for a period of time. The OHLC Series operates with a special kind of data in the form of four parameters defining the stock market - **open**, **high**, **low**, and **close**. The **high** and **low** values show the price range (the highest and lowest prices) over one unit of time. The open and close values indicate the opening and closing price of the stock for the corresponding period

## Example

The following example shows how to create a basic `RadCartesianChart` with an OHLC Series in XAML and C#.

1. Define the Cartesian Chart.

 ```XAML
<telerikChart:RadCartesianChart PaletteName="Light"
                                SelectionPaletteName="LightSelected"
                                BackgroundColor="White" >
    <telerikChart:RadCartesianChart.BindingContext>
        <local:ViewModel />
    </telerikChart:RadCartesianChart.BindingContext>
    <telerikChart:RadCartesianChart.HorizontalAxis>
        <telerikChart:DateTimeContinuousAxis LineColor="#A9A9A9"
                                             LabelFitMode="Rotate"
                                             LabelFormat="MMM"
                                             PlotMode="BetweenTicks"
                                             MajorStepUnit="Month"/>
    </telerikChart:RadCartesianChart.HorizontalAxis>
    <telerikChart:RadCartesianChart.VerticalAxis>
        <telerikChart:NumericalAxis LineColor="#A9A9A9"
                                    MajorTickBackgroundColor="#A9A9A9" />
    </telerikChart:RadCartesianChart.VerticalAxis>
    <telerikChart:RadCartesianChart.Series>
        <telerikChart:OhlcSeries CategoryBinding="Category"
                                 OpenBinding="Open"
                                 HighBinding="High"
                                 LowBinding="Low"
                                 CloseBinding="Close"
                                 ItemsSource="{Binding SeriesData}" />
    </telerikChart:RadCartesianChart.Series>
</telerikChart:RadCartesianChart>
 ```

1. Define the business model:

 ```C#
public class OhlcDataPoint : NotifyPropertyChangedBase
{
    private DateTime category;
    private double open;
    private double high;
    private double low;
    private double close;

    public DateTime Category
    {
        get { return this.category; }
        set
        {
            if (value != this.category)
            {
                this.category = value;
                this.OnPropertyChanged();
            }
        }
    }

    public double Open
    {
        get { return this.open; }
        set
        {
            if (value != this.open)
            {
                this.open = value;
                this.OnPropertyChanged();
            }
        }
    }

    public double High
    {
        get { return this.high; }
        set
        {
            if (value != this.high)
            {
                this.high = value;
                this.OnPropertyChanged();
            }
        }
    }

    public double Low
    {
        get { return this.low; }
        set
        {
            if (value != this.low)
            {
                this.low = value;
                this.OnPropertyChanged();
            }
        }
    }

    public double Close
    {
        get { return this.close; }
        set
        {
            if (value != this.close)
            {
                this.close = value;
                this.OnPropertyChanged();
            }
        }
    }
}
 ```

The following image shows the end result:

![Basic OhlcSeries](images/ohlc_series.png)

## See Also

- [Candlestick Series Overview]({%slug chart-series-candlestick-series%})
- [Financial Indicators]({%slug chart-series-financial-indicators%})
