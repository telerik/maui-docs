---
title: Creating Charts with Multiple Axes
page_title: Creating Charts with Multiple Horizontal and Vertical Axes - .NET MAUI Knowledge Base
description: Learn how to create a Telerik UI for .NET MAUI Chart component showing two vertical and a horizontal axis at the same time.
type: how-to
slug: chart-multiple-axis
tags: maui, chart, axis, multiple axis, second axis, vertical axis
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 4.0.0 | Telerik UI for .NET MAUI Chart | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 


## Description

How can I create a chart with multiple axes when I want to add a second horizontal or vertical axis?

## Solution

To solve this issue, create two separate Charts together and add a transparent background to the top chart.

>important By using the Axis `Location` property, you can specify the axis position. The supported options are Right` and `Left` for vertical axes, and `Top` and `Bottom` for horizontal axes.

The following example shows the XAML code for implementing the suggested approach:

```XAML
<Grid>
    <!-- bottom chart -->
    <telerik:RadCartesianChart x:Name="chart" >
        <telerik:RadCartesianChart.HorizontalAxis>
            <telerik:CategoricalAxis ShowLabels="True" />
        </telerik:RadCartesianChart.HorizontalAxis>
        <telerik:RadCartesianChart.VerticalAxis>
            <telerik:NumericalAxis Location="Right"
                                   ShowLabels="True"/>
        </telerik:RadCartesianChart.VerticalAxis>
        <telerik:RadCartesianChart.Series>
            <telerik:LineSeries CategoryBinding="Category"
                                ValueBinding="Value"
                                ShowLabels="True"
                                ItemsSource="{Binding Data}" />
        </telerik:RadCartesianChart.Series>
    </telerik:RadCartesianChart>

    <!-- top chart -->
    <telerik:RadCartesianChart x:Name="chart2"
                               BackgroundColor="Transparent">
        <telerik:RadCartesianChart.HorizontalAxis>
            <telerik:CategoricalAxis LabelTextColor="Transparent"
                                     LineColor="Transparent"
                                     ShowLabels="False"/>
        </telerik:RadCartesianChart.HorizontalAxis>
        <telerik:RadCartesianChart.VerticalAxis>
            <telerik:NumericalAxis ShowLabels="True"/>
        </telerik:RadCartesianChart.VerticalAxis>
        <telerik:RadCartesianChart.Series>
            <telerik:LineSeries CategoryBinding="Category"
                                ValueBinding="Value"
                                ShowLabels="True"
                                ItemsSource="{Binding Data1}" />
        </telerik:RadCartesianChart.Series>
    </telerik:RadCartesianChart>
</Grid>
```
