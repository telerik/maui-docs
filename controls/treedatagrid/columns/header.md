---
title: Column Headers
page_title: .NET MAUI DataGrid Documentation - Columns Header
description: Learn how to style and customize the text in the Telerik UI for .NET MAUI DataGrid Header by using the properties of the component.
position: 2
slug: datagrid-column-header
---


# .NET MAUI TreeDataGrid Column Headers

This article will guide you through the usage of the column headers, their customization as well through performing different data operations. Column headers are always visible by default. You can further customize the headers by using the `HeaderStyle` property.

## Changing the Text in the Header

To customize text inside the header, you use the `HeaderText` property. The property is per column. If `HeaderText` is not set, the text inside the `PropertyName` is displayed.

```XAML
<telerik:RadTreeDataGrid x:Name="dataGrid" 
					     AutoGenerateColumns="False">
	<telerik:RadDataGrid.Columns>
		<telerik:DataGridTextColumn PropertyName="Capital" 
									HeaderText="Capital Header"/>
		<telerik:DataGridTextColumn PropertyName="Country" 
									HeaderText="Country Header"/>
	</telerik:RadDataGrid.Columns>
</telerik:RadTreeDataGrid>
```

## Sorting

The user of the application can sort a particular column by tapping on its header. When the data is sorted by a column, the sort indicator shows in the header.

To learn more about the sorting functionality of the [.NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}), take a look at the [Sorting]({%slug treedatagrid-sorting-overview%}) article.

## Filtering

The header of the column hosts the built-in filtering mechanism (the filter indicator which opens the Filtering UI), which allows the user to filter the data by the columns' values.

To learn more about the filtering functionality, take a look at the [Filtering]({%slug treedatagrid-filtering-overview%}) article.

## Styling 

Use the `HeaderStyle` property to style the `DataGridColumn` header.

## Header Content Customization

You can customize the content of the Header using the `HeaderContentTemplate`(`DataTemplate`) property.

To define the `DataTemplate` for the header:

<snippet id='datagrid-headercontenttemplate-datatemplate' />

## Color on Hover

You can change the hover state background color of the column header by setting the `BackgroundColor` property.

The following example demonstrates how to apply the `BackgroundColor` property to the DataGrid `HeaderContentTemplate` for its hover visual state: 

```XAML
<DataTemplate x:Key="CustomHeaderTemplate">
    <telerik:RadBorder BackgroundColor="#F8F8F8"
                       BorderThickness="1">
        <VisualStateManager.VisualStateGroups>
            <VisualStateGroup x:Name="CommonStates">
                <VisualState x:Name="Normal" />
                <VisualState x:Name="Focused" />
                <VisualState x:Name="Disabled" />
                <VisualState x:Name="PointerOver">
                    <VisualState.Setters>
                        <Setter Property="BackgroundColor" Value="#33000000" />
                    </VisualState.Setters>
                </VisualState>
            </VisualStateGroup>
        </VisualStateManager.VisualStateGroups>
    </telerik:RadBorder>
</DataTemplate>
```

## Customizing the Column

Customize the column header by using the `HeaderContentTemplate`(of type `DataTemplate`) to achieve the desired full customization of the column. The property demonstrates the ability of the DataGrid to specify and show custom appearance for the column headers.

## See Also

- [Columns Cells Templates]({%slug treedatagrid-cell-templates%})
- [Column Footers]({%slug treedatagrid-column-footer%})
- [Column Resizing]({%slug treedatagrid-column-resizing%})
- [Columns Width]({%slug treedatagrid-columns-width%})
- [Frozen Columns]({%slug treedatagrid-frozen-columns%})
- [Columns Reordering]({%slug treedatagrid-columns-reordering%})
