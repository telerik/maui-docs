---
title: Cartesian Chart
page_title: .NET MAUI Chart Documentation - Cartesian Chart
position: 1
description: Check our &quot;Cartesian Chart&quot; documentation article for Telerik Chart for .NET MAUI.
previous_url: /controls/chart/types/chart-types-cartesian-chart
slug: chart-types-cartesian-chart
---

# .NET MAUI Cartesian Chart

The Cartesian Chart visualizes its data points by using the Cartesian coordinate system. The X and Y axes define how the coordinates of each point in the plot area are calculated and the series type defines the way these data points will be visualized.  

## Properties

The Cartesian Chart supports the following properties:

* `HorizontalAxis` (`CartesianAxis`)&mdash;Gets or sets the visual `Axis` instance that will be used to plot points along the horizontal (X) axis.
* `VerticalAxis` (`CartesianAxis`)&mdash;Gets or sets the visual `Axis` instance that will be used to plot points along the vertical (Y) axis.
* `Series` (`ElementsCollection<CartesianSeries>`)&mdash;Gets a collection of all series presented by the chart instance.
* `Palette` (`ChartPalette`)&mdash;Gets or sets the `ChartPalette` instance that defines the appearance of the chart.
* `PaletteName` (`PaletteNames`)&mdash;Gets or sets the name of the predefined `Palette` that will be applied to the chart.
* `SelectionPalette` (`ChartPalette`)&mdash;Gets or sets the `ChartPalette` instance that defines the appearance of the chart for selected series and/or data points.
* `SelectionPaletteName` (`PaletteNames`)&mdash;Gets or sets the name of the predefined `SelectionPalette` that will be applied to the chart.
* `ChartBehaviors` (`ObservableCollection<ChartBehavior>`)&mdash;Gets a collection of all enabled behaviors.
* `Grid` (`CartesianChartGrid`)&mdash;Gets or sets the `CartesianChartGrid` instance used to decorate the chart plot area with grid and strip lines.
* `Annotations` (`ObservableCollection<CartesianChartAnnotation>`)&mdash;Gets a collection of all annotations presented by the chart instance.
* `MaxZoom` (`Size`)&mdash;Gets or sets the maximum allowed zoom.
* `Zoom` (Size zoom)&mdash;Gets or sets the zoom of the chart.
* `PanOffset` (Point offset)&mdash;Gets or sets an offset to the chart. Note that the offset will be specific for every platform depending on the values that the platform works with (absolute pixels or normed to the axis range) and the axis type.

## Axes

The Cartesian Chart requires two axes which are used to calculate correctly the position of each data point. Usually one of the axes is used to display the category of each data point and the other represents its value.

The following Cartesian Chart axes are available:

- [Categorical axis]({% slug axes-categorical-axis %})&mdash;Arranges the plotted data points in categories where the key of each category is the point’s value (if available) for that axis or its index within the points collection. The coordinate of the point, specified by this axis, is discrete and is calculated depending on the size of the category slot where the point resides.
- [Numerical axis]({% slug axes-numerical-axis %})&mdash;Calculates the coordinate of each data point, depending on the actual numerical value this point provides for the axis. Exposes the `Minimum` and `Maximum` properties to allow you to explicitly define the range of values visible on this axis. If these properties are not specified, the axis will automatically calculate the range depending on the minimum and maximum data point values.
- [Date-Time Continuous axis]({% slug axes-date-time-continuous-axis %})&mdash;A special axis that expects each data point to provide a `System.DateTime` structure as its value for this axis. Think of this axis as a time line where the coordinate of each data point is calculated depending on the position of its associated date and time on the time line. The base unit (or the step) of the axis is calculated depending on the smallest difference between any two dates.

## Series

The Cartesian Chart supports the Categorical, Scatter, and Financial series.

### Categorical Cartesian Chart Series

The categorical Cartesian Chart series require a [Numerical]({% slug axes-numerical-axis %}) and a [Categorical]({% slug axes-categorical-axis %}) or [Date-Time Continuous]({% slug axes-date-time-continuous-axis %}) axes to get properly plotted.

The Categorical Cartesian Chart supports the following series:

- [Bar Series]({% slug chart-series-bar-series %})&mdash;Data points are represented by a box where the height (width) of the box is the distance between the numerical value of the point and the categorical axis that plots the point. Bars may be either horizontal or vertical depending on whether the categorical axis is specified as an `"X-axis"` or as a `"Y-axis"`.
- [Line Series]({% slug chart-series-line-series %})&mdash;Data points are connected with straight line segments.
- [Spline Series]({% slug chart-series-spline-series %})&mdash;Data points are connected with smooth line segments.
- [Area Series]({% slug chart-series-area-series %})&mdash;Data points and the corresponding coordinate axis enclose an area that may be optionally stroked and/or filled.
- [Spline Area Series]({% slug chart-series-spline-area-series %})&mdash;An area where points are connected with smooth rather than straight segments.

You can combine each of the above series of the same type in [stacks or clusters]({% slug chart-series-combine-mode %}). Combinations are formed when more than one data point from different series fall within the same category. The Cluster combine mode will position such points next to each other while the Stack combine mode will arrange such points in a stack-like structure. When stacks are formed, the numerical axis (if present) will consider each stack as a single entity and its sum will be the actual used value rather than the value of each point.

### Scatter Cartesian Chart Series

The Scatter Cartesian Charts Series require two Numerical axes to get properly plotted. Scattered data provides both the X and the Y coordinate.

The Scatter Cartesian Chart supports the following series:

- [Scatter Point Series]({% slug chart-series-scatter-point-series %})&mdash;Data points are represented by an arbitrary template.
- [Scatter Line Series]({% slug chart-series-scatter-line-series %})&mdash;Data points are connected with straight line segments.
- [Scatter Spline Series]({% slug chart-series-scatter-spline-series %})&mdash;Data points are connected with smooth line segments.
- [Scatter Area Series]({% slug chart-series-scatter-area-series %})&mdash;Data points and the horizontal axis enclose an area that may be optionally stroked and/or filled.
- [Scatter Spline Area Series]({% slug chart-series-scatter-spline-area-series %})&mdash;A ScatterArea Chart where points are connected with smooth rather than straight segments.

### Financial Cartesian Chart Series

The Financial Cartesian Chart Series require a [Numerical]({%slug axes-numerical-axis%}) and a [Date-Time Continuous]({%slug axes-date-time-continuous-axis%}) or [Categorical]({%slug axes-categorical-axis%}) axes to get properly plotted.

The Financial Cartesian Chart supports the following series:

- [OHLC Series]({%slug chart-series-ohlc-series%})&mdash;Each data point is visualized as a line with an **open** and **close** value indicators on its side.
- [Candlestick Series]({%slug chart-series-candlestick-series%})&mdash;Data points are plotted as visuals that resemble candlesticks.
- [Financial Indicators Series]({%slug chart-series-financial-indicators%})&mdash;The financial, or also called stock indicators, are mainly used for keeping track of stock prices and patterns of price changes over time.

## Customize the Chart Colors

You can take advantage of the available customization options the Chart control provides. You can change the default Chart and series colors by setting a `Palette`. For more details on the suggested implementation, see the [Creating Custom Chart Palettes KB article]({%slug chart-how-to-create-custom-palette%}).

## Example

**1.** Define the `RadCartesianChart`:

```XAML
<telerik:RadCartesianChart>
</telerik:RadCartesianChart>
```

**2.** The `RadCartesianChart` requires you to set a horizontal and a vertical axis to plot its data.

```XAML
<telerik:RadCartesianChart.HorizontalAxis>
	<telerik:CategoricalAxis/>
</telerik:RadCartesianChart.HorizontalAxis>
<telerik:RadCartesianChart.VerticalAxis>
	<telerik:NumericalAxis/>
</telerik:RadCartesianChart.VerticalAxis>
```

**3.** Now, add the series to the `RadCartesianChart.Series` collection:

```XAML
<telerik:RadCartesianChart>
	<telerik:RadCartesianChart.Series>
		<telerik:BarSeries ItemsSource="{Binding CategoricalData}">
			<telerik:BarSeries.ValueBinding>
				<telerik:PropertyNameDataPointBinding PropertyName="Value"/>
			</telerik:BarSeries.ValueBinding>
			<telerik:BarSeries.CategoryBinding>
				<telerik:PropertyNameDataPointBinding PropertyName="Category"/>
			</telerik:BarSeries.CategoryBinding>
		</telerik:BarSeries>
	</telerik:RadCartesianChart.Series>
</telerik:RadCartesianChart>
```

**4.** Set the `BindingContext` of the chart if none of its parents has a context:

 ```XAML
<telerik:RadCartesianChart.BindingContext>
	<local:ViewModel/>
</telerik:RadCartesianChart.BindingContext>
 ```

**5.** In the example, `local` is defined as follows:

```XAML
xmlns:local="clr-namespace:[The namespace where the ViewModel class is defined];assembly=[The assembly name]"
```

## Cartesian Chart Example

The following example shows the full definition of the chart.

**1.** Create the needed business object, for example:

<snippet id='categorical-data-model' />


**2.** Create a `ViewModel`:

<snippet id='chart-series-categorical-data-view-model' />

**3.** Declare the chart in XAML:

```XAML
<telerik:RadCartesianChart>
    <telerik:RadCartesianChart.BindingContext>
        <local:CategoricalDataViewModel />
    </telerik:RadCartesianChart.BindingContext>
    <telerik:RadCartesianChart.HorizontalAxis>
        <telerik:CategoricalAxis LabelFitMode="MultiLine" />
    </telerik:RadCartesianChart.HorizontalAxis>
    <telerik:RadCartesianChart.VerticalAxis>
        <telerik:NumericalAxis LabelFitMode="MultiLine" />
    </telerik:RadCartesianChart.VerticalAxis>
    <telerik:RadCartesianChart.Series>
        <telerik:BarSeries ValueBinding="Value"
                                CategoryBinding="Category"
                                ItemsSource="{Binding Data}" />
    </telerik:RadCartesianChart.Series>
</telerik:RadCartesianChart>
```


The following image shows the final result:

![Cartesian Chart](images/cartesian-bar-series-basic-example.png)

For a sample example 

## See Also

- [Pie Chart]({%slug chart-types-pie-chart%})
- [Chart Legend]({%slug chart-features-legend%})
- [Chart Null Values]({%slug chart-nullvalues%})
