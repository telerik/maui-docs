---
title: Column Headers
page_title: .NET MAUI DataGrid Documentation - Columns Header
description: Check our &quot;Columns Header&quot; documentation article for Telerik DataGrid for .NET MAUI.
position: 2
previous_url: /controls/datagrid/columns/column-header
slug: datagrid-column-header
---


# .NET MAUI DataGrid Column Headers

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

## Sorting

You can sort a particular column tapping on its header. When the data is sorted by a column, its header changes its appearance and shows the sort direction via an indicator.

![.NET MAUI DataGrid Column Header Sorting indicator](../images/column-header-sorting.png)

To learn more about the sorting functionality take a look at the [Sorting]({%slug datagrid-sorting-overview%}) article.

## Filtering

The header of the column hosts the built-in filtering mechanism (the filter indicator which opens the Filtering UI), which allows you to filter the data by the columns' values.

![.NET MAUI DataGrid Column Header filter indicator](../images/column-header-filtering.png)

To learn more about the filtering functionality take a look at the [Filtering]({%slug datagrid-filtering-overview%}) article.

## Styling 

Use the `HeaderStyle` property to style the `DataGridColumn` header.

Check the [.NET MAUI DataGrid Column Header Styling]({%slug datagrid-columns-styling%}#headerstyle) topic for more information about the styling options you can use. 

## Header Content Customization

You can customize the content of the Header using the `HeaderContentTemplate`(`DataTemplate`) property.

Define the `DataTemplate` for the header:

<snippet id='datagrid-headercontenttemplate-datatemplate' />

Define the `HeaderContentTemplate` in the DataGrid column:

<snippet id='datagrid-headerfootercontenttemplate' />

![.NET MAUI DataGrid Column Header Template](../images/header-content-template.png)

## Achieve full customization of the column

You can customize the Column Header using the existing `HeaderContentTemplate` to achieve the desired full customization of the column.

## Hover Visual State on Column Header

You can change the background color of the column header on Hover visual state by setting the `BackgroundColor` property.

Here is an example how to achieve the desired result:

```XAML
 <VisualStateManager.VisualStateGroups>
    <VisualStateGroup x:Name="CommonStates">
        <VisualState x:Name="Normal" />
        <VisualState x:Name="Focused" />
        <VisualState x:Name="Disabled" />
        <VisualState x:Name="PointerOver">
             <VisualState.Setters>
                <Setter Property="BackgroundColor" Value="Yellow" />
             </VisualState.Setters>
        </VisualState>
    </VisualStateGroup>
</VisualStateManager.VisualStateGroups>
```

And the result from the code snippet:

![DataGrid Header Column Background Color](../columns/images/datagrid-hover-background-color.gif)


## See Also

- [Text Column]({%slug datagrid-columns-text-column%})
- [Picker Column]({%slug datagrid-columns-picker-column%})
- [Template Column]({%slug datagrid-columns-template-column%})
