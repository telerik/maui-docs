---
title: Financial Indicators
page_title: .NET MAUI Chart Documentation | Financial Indicators
slug: chart-series-financial-indicators
description: Check our &quot;Financial Indicators&quot; documentation article for Telerik Chart for .NET MAUI
position: 2
---

# Financial Indicators

The financial, or also called stock, indicators are mainly used for keeping track of stock prices and patterns of price changes over time. For more information about what indicators are and what their purpose is, refer to the [Short information about financial indicators](https://www.investopedia.com/terms/t/technicalindicator.asp) article.

In terms of using the indicators in the `RadCartesianChart`, you need to add them in the same way you add any other Cartesian series. Every indicator has a related formula by which it calculates the expected result. All you need to do is provide the needed data.

In terms of setting their properties and getting them ready for displaying your stock data, the financial indicators are two types:

* Indicators that have a category and a value binding (usually the **close** one) as well as one or more periods:  

  * `OscillatorIndicator`
  * `RateOfChangeIndicator`
  * `RelativeStrengthIndexIndicator`
  * `TrixIndicator`
  * `WeightedMovingAverageIndicator`
  * `ExponentialMovingAverageIndicator`
  * `AdaptiveMovingAverageKaufmanIndicator`
  * `BollingerBandsIndicator`
  * `RelativeMomentumIndexIndicator`
  * `MacdIndicator`

* Indicators that have a category and **high**, **low**, or **close** value bindings as well as none, one, or more periods:

  * `AverageTrueRangeIndicator`
  * `CommodityChannelIndexIndicator`
  * `StochasticFastIndicator`
  * `StochasticSlowIndicator`
  * `TrueRangeIndicator`
  * `UltimateOscillatorIndicator`

## Example

The following example shows how to create a basic `RadCartesianChart` with an OHLC Series and how to set a couple of `ExponentialMovingAverageIndicator` instances with different periods.

1. Define the `RadCartesianChart`.

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
                                             LabelFormat="dd/MM"
                                             PlotMode="BetweenTicks"
                                             MajorStep="2"
                                             MajorStepUnit="Day"/>
    </telerikChart:RadCartesianChart.HorizontalAxis>
    <telerikChart:RadCartesianChart.VerticalAxis>
        <telerikChart:NumericalAxis LineColor="#A9A9A9"
                                    Minimum="320"
                                    Maximum="350"
                                    MajorTickBackgroundColor="#A9A9A9" />
    </telerikChart:RadCartesianChart.VerticalAxis>
    <telerikChart:RadCartesianChart.Series>
        <telerikChart:OhlcSeries CategoryBinding="Category"
                                 DisplayName="AppleStocks-OHLC"
                                 OpenBinding="Open"
                                 HighBinding="High"
                                 LowBinding="Low"
                                 CloseBinding="Close"
                                 ItemsSource="{Binding SeriesData}"/>

        <telerikChart:ExponentialMovingAverageIndicator CategoryBinding="Category"
                                                        DisplayName="EMA 7days"
                                                        ValueBinding="Close"
                                                        Period="7"
                                                        StrokeThickness="1"
                                                        Stroke="DarkGreen"
                                                        ItemsSource="{Binding SeriesData}"/>

        <telerikChart:ExponentialMovingAverageIndicator CategoryBinding="Category"
                                                        DisplayName="EMA 14days"
                                                        ValueBinding="Close"
                                                        Period="14"
                                                        StrokeThickness="1"
                                                        Stroke="DarkOrange"
                                                        ItemsSource="{Binding SeriesData}"/>
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

![Financial Indicators](images/indicators_series.png)

## See Also

- [Ohlc Series Overview]({%slug chart-series-ohlc-series%})
- [Candlestick Series Overview]({%slug chart-series-candlestick-series%})
