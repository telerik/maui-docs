---
title: Column Footers
page_title: .NET MAUI TreeDataGrid Documentation - Columns Footer
description: Learn how to visualize a column footer in the Telerik TreeDataGrid for .NET MAUI control.
position: 3
slug: treedatagrid-column-footer
---


# .NET MAUI TreeDataGrid Column Footers

The [Telerik UI for .NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) allows you to display additional information which applies to the columns in a specific row placed at the bottom of the control. This row consists of individual footer cells for each column.

By default, column footers are hidden. To make them visible, set the `ShowColumnFooters` property to `True`.

The following example shows how to define a footer in the TreeDataGrid:

```XAML
<telerik:RadTreeDataGrid x:Name="dataGrid" 
                         ShowColumnFooters="True"/>
```

## Setting Text in the Footer

To define a text inside the footer, use the `FooterText` property. The property is per column:

```XAML
<telerik:RadTreeDataGrid x:Name="dataGrid" 
						 ShowColumnFooters="True" 
						 AutoGenerateColumns="False">
	<telerik:RadDataGrid.Columns>
		<telerik:DataGridTextColumn PropertyName="Capital" 
									FooterText="Capital Footer"/>
		<telerik:DataGridTextColumn PropertyName="Country" 
									FooterText="Country Footer"/>
	</telerik:RadDataGrid.Columns>
</telerik:RadTreeDataGrid>
```

> Define the footer per column; otherwise, the cell will appear empty.

## Styling 

Use the `FooterStyle` property to style the footer of the columns in the TreeDataGrid.

## Footer Content Customization

You can customize the content of the footer by using the `FooterContentTemplate`(`DataTemplate`) property.

## See Also

- [Columns Cells Templates]({%slug treedatagrid-cell-templates%})
- [Column Resizing]({%slug treedatagrid-column-resizing%})
- [Columns Width]({%slug treedatagrid-columns-width%})
- [Frozen Columns]({%slug treedatagrid-frozen-columns%})
- [Columns Reordering]({%slug treedatagrid-columns-reordering%})
