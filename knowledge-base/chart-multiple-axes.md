---
title: Chart with multiple axis
description: Create chart with two vertical axis, horizontal axis.
type: how-to
page_title: Chart with multiple horizontal and vertical axis.
slug: chart-multiple-axis
position: 
tags: maui, chart, axis, muliple axis, second axis, vertical axis
res_type: kb
---

## Environment

<table>
	<tbody>
		<tr>
			<td>Product Version</td>
			<td>4.0.0</td>
		</tr>
		<tr>
			<td>Product</td>
			<td>Chart for .NET MAUI</td>
		</tr>
	</tbody>
</table>

## Description

This article explains how to create chart with muliple axis. If you want to add second horizontal and or vertical axis.

## Solution

Add 2 separate Charts together and have a transparent background on the top chart.

>important Using the Axis `Location` property you can specify the axis position. The options are &mdash;`Right`, `Left` for vertical axis and `Top`, `Bottom` for horizontal axis.

This is the XAML code:

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

