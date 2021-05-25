---
title: Chart Legend
page_title: .NET MAUI Chart Documentation | Chart Legend 
slug: chart-features-legend
description: Check our &quot;Chart Legend&quot; documentation article for Telerik Chart for .NET MAUI.
position: 9
---

# Chart Legend

The Legend feature of the **RadChart** makes it easy for you to provide description regarding the series which are visualized within the control. In order to add the legend feature in your application, you need to initialize a new object of type **RadLegend**. 

Chart Legend definition:

```XAML
<telerikChart:RadPieChart x:Name="pieChart" HeightRequest="300">
    <telerikChart:RadCartesianChart.BindingContext>
        <local:ViewModel />
    </telerikChart:RadCartesianChart.BindingContext>
    <telerikChart:RadPieChart.Series>
        <telerikChart:PieSeries DisplayName="Value" LegendTitleBinding="Category" ItemsSource="{Binding Data1}" ValueBinding="Value"/>
    </telerikChart:RadPieChart.Series>
</telerikChart:RadPieChart>
<telerikChart:RadLegend HeightRequest="200" 
                        LegendItemFontColor="DarkGreen"
                        LegendItemFontSize="20"
                        LegendProvider="{x:Reference Name=pieChart}"/>
```

### **Figure 1: RadLegend in combination with PieChart**

![Pie Chart legend](images/piechart-legend.png)

As shown in **Figure 1**, each item within the **RadLegend** represents particular series. The most important property which you need to set is the **LegendProvider**. It should point to the chart object whose series will be included in the legend. 

Here are the most important properties of the **RadLegend** control. In brackets is commented the type of the property:

* **LegendProvider**(RadChartBase): The Chart control whose series will be described in the legend.
* **LegendItemFontSize**(double): The size of the item's title text.
* **LegendItemFontColor**(Color): The color of the item's title text.
* **LegendItemIconSize**(Size): The size of the title icons.
* **Orientation**(LegendOrientation): Sets the orientation of the legend. Can be Horizontal or Vertical.


The control can be used in combination with **RadCartesianChart** as well. 

```XAML
<telerikChart:RadCartesianChart x:Name="chart" HeightRequest="300">
  <telerikChart:RadCartesianChart.BindingContext>
    <local:ViewModel />
  </telerikChart:RadCartesianChart.BindingContext>
  <telerikChart:RadCartesianChart.HorizontalAxis>
    <telerikChart:CategoricalAxis />
  </telerikChart:RadCartesianChart.HorizontalAxis>
  <telerikChart:RadCartesianChart.VerticalAxis>
    <telerikChart:NumericalAxis />
  </telerikChart:RadCartesianChart.VerticalAxis>
  <telerikChart:RadCartesianChart.Series>
    <telerikChart:LineSeries CategoryBinding="Category" 
                            ValueBinding="Value" 
                            DisplayName=" Data1"
                            ItemsSource="{Binding Data1}" />
    <telerikChart:LineSeries CategoryBinding="Category" 
                             ValueBinding="Value" 
                             DisplayName=" Data2"
                             ItemsSource="{Binding Data2}" />
    <telerikChart:LineSeries CategoryBinding="Category" 
                             ValueBinding="Value" 
                             DisplayName=" Data3"
                             ItemsSource="{Binding Data3}" />
  </telerikChart:RadCartesianChart.Series>
</telerikChart:RadCartesianChart>
    <telerikChart:RadLegend LegendProvider="{x:Reference Name=chart}" 
                            LegendItemFontColor="DarkGreen"
                            HeightRequest="200"/>
```

### **Figure 2: RadLegend in combination with CartesianChart**

![Cartesian Chart legend](images/cartesianchart-legend.png)

## LegendTitleBinding

The **LegendTitleBinding** is a property which can be set specifically for the **PieSeries**. It points to the property of the data item which will be used as a title in the legend. For all other series, the **DisplayName** property will be used instead.

```XAML
<telerikChart:RadPieChart.Series>
    <telerikChart:PieSeries DisplayName="Value" 
							LegendTitleBinding="Category" 
							ItemsSource="{Binding Data1}" 
							ValueBinding="Value"/>
</telerikChart:RadPieChart.Series>
```

## See Also

- [CartesianChartGrid]({%slug cartesian-chart-grid%})
- [Annotations]({%slug chart-annotations%})
