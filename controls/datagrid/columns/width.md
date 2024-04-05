---
title: Columns Width
page_title: .NET MAUI DataGrid Documentation - Columns Width
description: Check our &quot;Columns Width&quot; documentation article for Telerik DataGrid for .NET MAUI.
position: 4
previous_url: /controls/datagrid/columns/datagrid-columns-width
slug: datagrid-columns-width
---

# .NET MAUI DataGrid Columns Width

This article describes how to set a width to the [.NET MAUI DataGrid]({%slug datagrid-overview%}) column using the `SizeMode` and `Width` properties.

* `SizeMode`(`DataGridColumnSizeMode`)&mdash;Defines the `DataGridColumnSizeMode` value that controls how the column and its associated cells are sized horizontally.
  * `Fixed`&mdash;The column has a fixed width as defined by its Width property.
  * `Stretch`&mdash;The column is stretched to the available width proportionally to its desired width.
  * `Auto`&mdash;The columns is sized to its desired width. That is the maximum desired width of all associated cells.
* `Width`(`double`)&mdash;Specifies the fixed width for the column. Applicable when the `SizeMode` property is set to `DataGridColumnSizeMode`.Fixed.
* `MinimumWidth`(`double`)&mdash;Specifies the minimum width of a column. This property is applicable when setting `SizeMode` column property to `Fixed`. When `MinimumWidth` is set, you can not reduce the width of the column to a value lower than the `MinimumWidth`. 

* `ActualWidth` (double): Gets the actual width of the column.

## Example

In this example, we are going to use the following business object:

<snippet id='datagrid-commands-editing-businessobject'/>

After you have created your collection of custom objects, you should assign it to the `ItemsSource` property of the control:

```C#
this.grid.ItemsSource = new List<Data>
{
    new Data { Country = "Columbia", Capital = "Bogota" },
    new Data { Country = "Germany", Capital = "Berlin" },
    new Data { Country = "Italy", Capital = "Rome" },
    new Data { Country = "France", Capital = "Paris" },
    new Data { Country = "Bulgaria", Capital = "Sofia" },
};
```

### First Scenario when SizeMode="Fixed":

```XAML
<telerik:RadDataGrid x:Name="grid" AutoGenerateColumns="False">
	<telerik:RadDataGrid.Columns>
		<telerik:DataGridTextColumn PropertyName="Country" HeaderText="Country" Width="100" SizeMode="Fixed"/>
		<telerik:DataGridTextColumn PropertyName="Capital" HeaderText="Capital" Width="200" SizeMode="Fixed"/>
	</telerik:RadDataGrid.Columns>
</telerik:RadDataGrid>
```

Where the `telerik` namespace is the following:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

>important The `Width` property of columns will apply only when `SizeMode="Fixed"`.

The first and second columns have set widths of 100 and 200, respectively:

![DataGrid Fixes Column Size](../images/datagrid-columns-width-fixed.png)

### Second Scenario when SizeMode="Stretch":

```XAML
<telerik:RadDataGrid x:Name="grid" AutoGenerateColumns="False">
	<telerik:RadDataGrid.Columns>
		<telerik:DataGridTextColumn PropertyName="Country" HeaderText="Country" Width="100" SizeMode="Stretch"/>
		<telerik:DataGridTextColumn PropertyName="Capital" HeaderText="Capital" Width="200" SizeMode="Stretch"/>
	</telerik:RadDataGrid.Columns>
</telerik:RadDataGrid>
```

Where the `telerik` namespace is the following:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

The columns take all the available space proportionally. The Width property is ignored.

![DataGrid Stretch Column Size](../images/datagrid-columns-width-stretch.png)

### Third Scenario when SizeMode="Auto":

```XAML
<telerik:RadDataGrid x:Name="grid" AutoGenerateColumns="False">
	<telerik:RadDataGrid.Columns>
		<telerik:DataGridTextColumn PropertyName="Country" HeaderText="Country" Width="100" SizeMode="Auto"/>
		<telerik:DataGridTextColumn PropertyName="Capital" HeaderText="Capital" Width="200" SizeMode="Auto"/>
	</telerik:RadDataGrid.Columns>
</telerik:RadDataGrid>
```

Where the `telerik` namespace is the following:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

The columns take only as much space as they need. The Width property is ignored.

![DataGrid Auto Column Size](../images/datagrid-columns-width-auto.png)

###  Fourth Scenario with different SizeMode values

Lastly, lets use three columns to fully clarify the `SizeMode` behavior:

```XAML
<telerik:RadDataGrid x:Name="grid" AutoGenerateColumns="False">
    <telerik:RadDataGrid.Columns>
        <telerik:DataGridTextColumn PropertyName="Country" HeaderText="Country" Width="100" SizeMode="Fixed"/>
        <telerik:DataGridTextColumn PropertyName="Capital" HeaderText="Capital" Width="200" SizeMode="Auto"/>
        <telerik:DataGridTextColumn PropertyName="Country" HeaderText="Country" Width="200" SizeMode="Stretch"/>
    </telerik:RadDataGrid.Columns>
</telerik:RadDataGrid>
```

Where the `telerik` namespace is the following:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

The first and the third columns each have a fixed size of 100 and the second column takes all the available space because of SizeMode="Stretch":

![DataGrid SizeMode](../images/datagrid-columns-width.png)

## See Also

- [Picker Column]({%slug datagrid-columns-picker-column %})
- [Template Column]({%slug datagrid-columns-template-column %})
- [Text Column]({%slug datagrid-columns-text-column %})
