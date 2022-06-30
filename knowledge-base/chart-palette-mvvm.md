---
title: Different color for each bar
description: Apply different bar chart colors using MVVM.
type: how-to
page_title: Different Chart Palette for Bar Series using MVVM pattern.
slug: chart-color-for-each-bar-mvvm
position: 
tags: maui, chart, barseries, chart color, bar color, mvvm
ticketid: 1567000
res_type: kb
---

## Environment
<table>
	<tbody>
		<tr>
			<td>Product Version</td>
			<td>2.0.0</td>
		</tr>
		<tr>
			<td>Product</td>
			<td>Chart for .NET MAUI</td>
		</tr>
	</tbody>
</table>


## Description
Currently the only way to add a Chart Palette is by adding a Palette entry in XAML. This article will show you how-to set a different color to the Chart Bar Series using MVVM manner.
In general you have to create a custom chart palette in the ViewModel

## Solution
This solution uses the code from Telerik UI for .NET MAUI documentation for Bar Series and adds the necessary components to achieve the desired result: 
https://docs.telerik.com/devtools/maui/controls/chart/series/cartesian/bar-series

* First, add the `Color` property to the business model:
```C#
public class DataItem
    {
        public string Category { get; set; }
        public double? Value { get; set; }
        public Color barColor { get; set; }
    }
```

* Second, set values for the `barColor` property of type `Color` in the Collection:
```C#
var seriesData = new ObservableCollection<DataItem>()
            {
                new DataItem(){Category = "Greenings", Value = 85, barColor = Color.FromRgba("#F8F8F8")},
                new DataItem(){Category = "Perfecto", Value = 78, barColor = Color.FromRgba("#F8A8F8")},
                new DataItem(){Category = "NearBy", Value = 99, barColor = Color.FromRgba("#F8F808")},
                new DataItem(){Category = "FamilyStore", Value = 85, barColor = Color.FromRgba("#B8F8F8")},
                new DataItem(){Category = "Fresh&Green", Value = 57, barColor = Color.FromRgba("#000000")}
            };
```

After creating the business model and the collection of data, create a class in the ViewModel that changes the values of the `Chart Palette`.

## Properties

* Create a Bindable property to store the Colors:
```C#
public static readonly BindableProperty ColorsSourceProperty = BindableProperty.CreateAttached("ColorsSource", typeof(IEnumerable), typeof(ChartUtils), null, propertyChanged: OnColorsSourceChanged);
```

* Define the properties which get and set the values in the collection:

```C#
public static IEnumerable GetColorsSource(BindableObject bindableObject)
        {
            return (IEnumerable)bindableObject.GetValue(ColorsSourceProperty);
        }

public static void SetColorsSource(BindableObject bindableObject, IEnumerable value)
        {
            bindableObject.SetValue(ColorsSourceProperty, value);
        }
```

## Methods

To get the desired color there should be a method which changes the old palette to a new one:
```C#
private static void OnColorsSourceChanged(BindableObject bindable, object oldValue, object newValue)
        {
            IEnumerable newColorsSource = (IEnumerable)newValue;
            RadCartesianChart chart = (RadCartesianChart)bindable;
            chart.Palette = ToChartPalette(newColorsSource);
        }
```

After having the `OnColorsSourceChanged` method we need one which will create new palette entries based on the data from `SeriesData` collection:
```C#
private static ChartPalette ToChartPalette(IEnumerable colorsSource)
        {
            ChartPalette chartPalette = new ChartPalette();

            if (colorsSource != null)
            {
                foreach (var item in colorsSource)
                {
                    if (item is DataItem dataItem)
                    {
                        PaletteEntry entry = new PaletteEntry();
                        entry.FillColor = dataItem.barColor;
                        entry.StrokeColor = dataItem.barColor;
                        chartPalette.Entries.Add(entry);
                    }
                }
            }

            return chartPalette;
        }
```

## Final Code

The final code looks as follows:
```C#
public static class ChartUtils
    {
        public static readonly BindableProperty ColorsSourceProperty = BindableProperty.CreateAttached("ColorsSource", typeof(IEnumerable), typeof(ChartUtils), null,
            propertyChanged: OnColorsSourceChanged);

        public static IEnumerable GetColorsSource(BindableObject bindableObject)
        {
            return (IEnumerable)bindableObject.GetValue(ColorsSourceProperty);
        }

        public static void SetColorsSource(BindableObject bindableObject, IEnumerable value)
        {
            bindableObject.SetValue(ColorsSourceProperty, value);
        }

        private static void OnColorsSourceChanged(BindableObject bindable, object oldValue, object newValue)
        {
            IEnumerable newColorsSource = (IEnumerable)newValue;
            RadCartesianChart chart = (RadCartesianChart)bindable;
            chart.Palette = ToChartPalette(newColorsSource);
        }

        private static ChartPalette ToChartPalette(IEnumerable colorsSource)
        {
            ChartPalette chartPalette = new ChartPalette();

            if (colorsSource != null)
            {
                foreach (var item in colorsSource)
                {
                    if (item is DataItem dataItem)
                    {
                        PaletteEntry entry = new PaletteEntry();
                        entry.FillColor = dataItem.barColor;
                        entry.StrokeColor = dataItem.barColor;
                        chartPalette.Entries.Add(entry);
                    }
                }
            }

            return chartPalette;
        }
    }
```

## XAML

Finally we can attach the `ChartUtils` class to the Chart in XAML:
```XAML
<telerik:RadCartesianChart chartPalettes:ChartUtils.ColorsSource="{Binding SeriesData}">
                    <telerik:RadCartesianChart.ChartBehaviors>
                        <telerik:ChartSelectionBehavior DataPointSelectionMode="Single" 
                                                             SeriesSelectionMode="None" />
                    </telerik:RadCartesianChart.ChartBehaviors>
                    <telerik:RadCartesianChart.HorizontalAxis>
                        <telerik:CategoricalAxis LineColor="#A9A9A9" 
                                                      MajorTickThickness="2" 
                                                      PlotMode="BetweenTicks" 
                                                      LabelFitMode="MultiLine" 
                                                      ShowLabels="True" 
                                                      MajorTickBackgroundColor="#A9A9A9" />
                    </telerik:RadCartesianChart.HorizontalAxis>
                    <telerik:RadCartesianChart.VerticalAxis>
                        <telerik:NumericalAxis LineColor="#A9A9A9" 
                                                    MajorTickBackgroundColor="#A9A9A9" 
                                                    Minimum="0" />
                    </telerik:RadCartesianChart.VerticalAxis>
                    <telerik:RadCartesianChart.Grid>
                        <telerik:CartesianChartGrid MajorLinesVisibility="Y" 
                                                         MajorLineThickness="1" />
                    </telerik:RadCartesianChart.Grid>
                    <telerik:RadCartesianChart.Series>
                        <telerik:BarSeries CategoryBinding="Category" 
                                           ValueBinding="Value"
                                           PaletteMode="DataPoint"
                                           ItemsSource="{Binding SeriesData}" />
                    </telerik:RadCartesianChart.Series>
                </telerik:RadCartesianChart>
```

>tip It is important to set `PaletteMode` to `DataPoint` otherwise the chart palettes won't apply.

## Final Result

![Chart Palette](images/chart-palette.png)