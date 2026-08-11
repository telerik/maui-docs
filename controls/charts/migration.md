---
title: Migrating to the New Charts
page_title: Migrating to the New Telerik UI for .NET MAUI Charts
description: Learn how to migrate from the previous Telerik UI for .NET MAUI Chart to the new Charts&mdash;updated namespaces, data binding, series, and axes.
components: ["charts"]
slug: charts-migration
position: 40
---

# Migrating to the New .NET MAUI Charts

The new Telerik UI for .NET MAUI Charts are built from the ground up to keep the familiar concepts&mdash;`RadCartesianChart`, `RadPieChart`, series, and axes&mdash;but expose a new namespace, simplified data binding, updated series, and axes properties. 

The new charts provide better performance, improved rendering, and a more consistent API across all chart types.

This article lists the differences between the Telerik MAUI Chart (implemented in the `Telerik.Maui.Controls.Compatibility.Chart` namespace) and the new Charts (implemented in the `Telerik.Maui.Controls.Charts` namespace), so you can update existing applications.

## Data Binding

Both the previous and the new charts populate their series through the `ItemsSource` property. The main difference is how each data point resolves its value and category.

The Compatibility Chart uses `DataPointBinding` objects (`PropertyNameDataPointBinding`) assigned to the `ValueBinding` and `CategoryBinding` properties. The new Charts replace these with the simpler `string`-based `HorizontalBinding` and `VerticalBinding` properties that directly point to the data-item member.

| Chart (`Telerik.Maui.Controls.Compatibility`) | Charts (`Telerik.Maui.Controls.Charts`) |
| --- | --- |
| `ItemsSource` (`IEnumerable`) | `ItemsSource` (`IEnumerable`) |
| `CategoryBinding` (`DataPointBinding`) | `HorizontalBinding` (`string`) |
| `ValueBinding` (`DataPointBinding`) | `VerticalBinding` (`string`) |
| `PropertyNameDataPointBinding { PropertyName = "..." }` | Property name assigned directly as a `string` |

>caption Chart (Telerik.Maui.Controls.Compatibility):

```XAML
<telerik:RadCartesianChart>
    <telerik:RadCartesianChart.BindingContext>
        <local:ViewModel />
    </telerik:RadCartesianChart.BindingContext>
    <telerik:RadCartesianChart.HorizontalAxis>
        <telerik:CategoricalAxis />
    </telerik:RadCartesianChart.HorizontalAxis>
    <telerik:RadCartesianChart.VerticalAxis>
        <telerik:NumericalAxis />
    </telerik:RadCartesianChart.VerticalAxis>
    <telerik:RadCartesianChart.Series>
        <telerik:BarSeries CategoryBinding="Category"
                           ValueBinding="Value"
                           ItemsSource="{Binding Data}" />
    </telerik:RadCartesianChart.Series>
</telerik:RadCartesianChart>
```

>caption Charts (Telerik.Maui.Controls.Charts):

```XAML
<charts:RadCartesianChart>
    <charts:RadCartesianChart.BindingContext>
        <models:CategoricalViewModel />
    </charts:RadCartesianChart.BindingContext>
    <charts:RadCartesianChart.Axes>
        <charts:CategoricalAxis />
        <charts:NumericalAxis />
    </charts:RadCartesianChart.Axes>
    <charts:RadCartesianChart.Series>
        <charts:BarSeries HorizontalBinding="Category"
                          VerticalBinding="Value"
                          ItemsSource="{Binding Data}" />
    </charts:RadCartesianChart.Series>
</charts:RadCartesianChart>
```

For more details, see the [Getting Started]({% slug charts-cartesian-getting-started %}) article.

## Namespaces

The namespaces and assembly references for the new Charts have changed. The following table lists the previous and new namespaces.

| Chart (Telerik.Maui.Controls.Compatibility) | Charts (Telerik.Maui.Controls.Charts) |
| --- | --- |
| `xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"` | `xmlns:charts="clr-namespace:Telerik.Maui.Controls.Charts;assembly=Telerik.Maui.Controls"` |
| `using Telerik.Maui.Controls.Compatibility.Chart;` | `using Telerik.Maui.Controls.Charts;` |

In both versions, register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method inside the `CreateMauiApp` method of the `MauiProgram.cs` file:

```C#
using Telerik.Maui.Controls.Compatibility;

public static class MauiProgram
{
    public static MauiApp CreateMauiApp()
    {
        var builder = MauiApp.CreateBuilder();
        builder
            .UseTelerik()
            .UseMauiApp<App>();
        return builder.Build();
    }
}
```

## Chart Types

Both versions provide the same chart types. The control classes keep their names.

| Chart (Telerik.Maui.Controls.Compatibility) | Charts (Telerik.Maui.Controls.Charts) |
| --- | --- |
| `RadCartesianChart` | `RadCartesianChart` |
| `RadPieChart` | `RadPieChart` |

## Features

The following table maps the previous Chart features to their counterparts in the new Charts.

| Feature | Chart (Telerik.Maui.Controls.Compatibility) | Charts (Telerik.Maui.Controls.Charts) |
| --- | --- | --- |
| Grid lines | `RadCartesianChart.Grid` (`CartesianChartGrid`) | `RadCartesianChart.Grid` (`CartesianChartGrid`) |
| Data point labels | `ChartSeries.ShowLabels` | `ChartSeries.ShowLabels` |
| Multiple series | Multiple series in `Series` collection |  Multiple series in `Series` collection |
| Palette | `RadChartBase.Palette` (`ChartPalette`) | `RadCartesianChart.Palette` (`ChartPalette`)  |
| Plot areas | - | [Plot Areas]({% slug charts-cartesian-plot-areas %}) |

## Chart Series

The core Cartesian and Pie series are available in the new Charts. 

Still the new chart is in a preview state, and some series are not yet implemented. The following table lists the Chart series and their counterparts in the new Charts.

### Cartesian Series

| Chart (Telerik.Maui.Controls.Compatibility) | Charts (Telerik.Maui.Controls.Charts) |
| --- | --- |
| `BarSeries` | [`BarSeries`]({% slug charts-cartesian-bar-series %}) |
| `LineSeries` | [`LineSeries`]({% slug charts-cartesian-line-series %}) |
| `AreaSeries` | [`AreaSeries`]({% slug charts-cartesian-area-series %}) |
| `ScatterPointSeries` | [`PointSeries`]({% slug charts-cartesian-point-series %}) |
| `SplineSeries`, `SplineAreaSeries` | - |
| `ScatterLineSeries`, `ScatterSplineSeries`, `ScatterAreaSeries`, `ScatterSplineAreaSeries` | - |

### Pie Series

| Chart (Telerik.Maui.Controls.Compatibility) | Charts (Telerik.Maui.Controls.Charts) |
| --- | --- |
| `PieSeries` | [`PieSeries`]({% slug charts-pie-series %}) |
| `DoughnutSeries` | [`DonutSeries`]({% slug charts-donut-series %}) |

### Financial Series

| Chart (Telerik.Maui.Controls.Compatibility) | Charts (Telerik.Maui.Controls.Charts) |
| --- | --- |
| `CandlestickSeries`, `OhlcSeries`, financial indicators | - |

The `PieSeries` data binding also changed. The previous Chart used `ValueBinding` (a `DataPointBinding`); the new `PieSeries` uses the `string`&mdash;based `ValueBinding` and `LabelBinding` properties.

## Chart Axes

The Cartesian axes keep their names and roles. Define them through the `HorizontalAxis` and `VerticalAxis` properties of the `RadCartesianChart`.

| Chart (Telerik.Maui.Controls.Compatibility) | Charts (Telerik.Maui.Controls.Charts) |
| --- | --- |
| `CategoricalAxis` | [`CategoricalAxis`]({% slug charts-cartesian-categorical-axis %}) |
| `NumericalAxis` | [`NumericalAxis`]({% slug charts-cartesian-numerical-axis %}) |
| `DateTimeContinuousAxis` | [`DateTimeAxis`]({% slug charts-cartesian-datetime-axis %}) |

>caption Chart (Telerik.Maui.Controls.Compatibility) axes:

```XAML
<telerik:RadCartesianChart.HorizontalAxis>
    <telerik:CategoricalAxis />
</telerik:RadCartesianChart.HorizontalAxis>
<telerik:RadCartesianChart.VerticalAxis>
    <telerik:NumericalAxis />
</telerik:RadCartesianChart.VerticalAxis>
```

>caption Charts (Telerik.Maui.Controls.Charts) axes:

```XAML
<telerik:RadCartesianChart.HorizontalAxis>
    <telerik:CategoricalAxis />
</telerik:RadCartesianChart.HorizontalAxis>
<telerik:RadCartesianChart.VerticalAxis>
    <telerik:NumericalAxis />
</telerik:RadCartesianChart.VerticalAxis>
```

## API Differences Summary

The following table summarizes the main differences between the previous and the new Charts:

| Area | Chart (Telerik.Maui.Controls.Compatibility) | Charts (Telerik.Maui.Controls.Charts) |
| --- | --- | --- |
| Namespace | `Telerik.Maui.Controls.Compatibility.Chart` | `Telerik.Maui.Controls.Charts` |
| XAML namespace | `http://schemas.telerik.com/2022/xaml/maui` | `clr-namespace:Telerik.Maui.Controls.Charts;assembly=Telerik.Maui.Controls` |
| Data binding | `ValueBinding`, `CategoryBinding` (`DataPointBinding`) | `VerticalBinding`, `HorizontalBinding` (`string`) |
| Cartesian series | Bar, Line, Area, Spline, Scatter families | Bar, Line, Area, Point |
| Pie series | `PieSeries`, `DoughnutSeries` | `PieSeries`, `DonutSeries` |
| Financial series | OHLC, Candlestick, indicators | - |
| Axes | `Categorical`, `Numerical`, `DateTimeContinuous` | `Categorical`, `Numerical`, `DateTime` |

## See Also

- [Charts Overview]({% slug charts-overview %})
- [CartesianChart Overview]({% slug charts-cartesian-overview %})
- [CartesianChart Getting Started]({% slug charts-cartesian-getting-started %})
- [PieChart Overview]({% slug charts-pie-overview %})
- [Bar Series]({% slug charts-cartesian-bar-series %})
- [Categorical Axis]({% slug charts-cartesian-categorical-axis %})
