---
title: Column Headers
page_title: .NET MAUI DataGrid Documentation - Columns Header
description: Check our &quot;Columns Header&quot; documentation article for Telerik DataGrid for .NET MAUI.
position: 2
slug: datagrid-column-header
---


# Column Headers

This article will guide you through the usage of the column headers, their customization as well through performing different data operations. Column headers are always visible and cannot be hidden.

![DataGrid Column Header](../images/column-header.png)

## Changing the text in the header

To customize text inside the header you have to use the `HeaderText` property. The property is per column. If `HeaderText` is not set, the text inside the `PropertyName` is displayed.

```XAML
<telerik:RadDataGrid x:Name="dataGrid" 
					 AutoGenerateColumns="False">
	<telerik:RadDataGrid.Columns>
		<telerik:DataGridTextColumn PropertyName="Capital" 
									HeaderText="Capital Header"/>
		<telerik:DataGridTextColumn PropertyName="Country" 
									HeaderText="Country Header"/>
	</telerik:RadDataGrid.Columns>
</telerik:RadDataGrid>
```

> Note that the header has to be defined per column otherwise the cell will appear empty.

## Sorting

You can easily sort a particular column tapping ot its header. When the data is sorted by a column, its header changes its appearance and shows the sort direction via an indicator.

![.NET MAUI DataGrid Column Header Sorting indicator](../images/column-header-sorting.png)

To learn more about the sorting functionality take a look at the [Sorting]({%slug datagrid-sorting-overview%}) article.

## Filtering

The header of the column hosts the built-in filtering mechanism (the filter indicator which opens the Filtering UI), which allows you to filter the data by the columns' values.

![.NET MAUI DataGrid Column Header filter indicator](../images/column-header-filtering.png)

To learn more about the filtering functionality take a look at the [Filtering]({%slug datagrid-filtering-overview%}) article.

## Styling 

Use the `HeaderStyle` property in order to style the DataGridColumn header.

Check the [.NET MAUI DataGrid Column Header Styling]({%slug datagrid-columns-styling%}#headerstyle) topic for more information about the styling options you can use. 

## Header Content Customization

You can easily customize the content of the Header using the `HeaderContentTemplate`(`DataTemplate`) property.

Define the `DataTemplate` for the header:

<snippet id='datagrid-headercontenttemplate-datatemplate' />

Define the `HeaderContentTemplate` in the DataGridColumn:

<snippet id='datagrid-headerfootercontenttemplate' />

![.NET MAUI DataGrid Column Header Template](../images/header-content-template.png)

## See Also

- [Text Column]({%slug datagrid-columns-text-column%})
- [Picker Column]({%slug datagrid-columns-picker-column%})
- [Template Column]({%slug datagrid-columns-template-column%})
