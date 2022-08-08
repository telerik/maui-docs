---
title: Column Footers
page_title: .NET MAUI DataGrid Documentation - Columns Footer
description: Check our &quot;Columns Footer&quot; documentation article for Telerik DataGrid for .NET MAUI.
position: 3
slug: datagrid-column-footer
---


# Column Footers

The DataGrid allows you to display additional information which applies to the columns in a specific row placed at the bottom of the control. This row consists of individual footer cells for each column.

![Column Footer](../images/column-footer.png)

By default, column footers are hidden and in order to make them visible you have to set the `ShowColumnFooters` property to True.

The following example shows how to define a footer in the DataGrid:

```XAML
<telerik:RadDataGrid x:Name="dataGrid" 
                     ShowColumnFooters="True"/>
```

## Setting text in the footer

To define a text inside the footer you have to use the `FooterText` property. The property is per column:

```XAML
<telerik:RadDataGrid x:Name="dataGrid" 
					 ShowColumnFooters="True" 
					 AutoGenerateColumns="False">
	<telerik:RadDataGrid.Columns>
		<telerik:DataGridTextColumn PropertyName="Capital" 
									FooterText="Capital Footer"/>
		<telerik:DataGridTextColumn PropertyName="Country" 
									FooterText="Country Footer"/>
	</telerik:RadDataGrid.Columns>
</telerik:RadDataGrid>
```

> Note that the footer has to be defined per column otherwise the cell will appear empty.

## Styling 

Use the `FooterStyle` property in order to style the DataGridColumn footer.

Check the [DataGrid Column Footer Styling]({%slug datagrid-columns-styling%}#footerstyle) topic for more information about the styling options you can use. 

## Footer Content Customization

You can easily customize the content of the footer using the `FooterContentTemplate`(`DataTemplate`) property.

Define the `DataTemplate` for the footer:

<snippet id='datagrid-footercontenttemplate-datatemplate' />

Define the `FooterContentTemplate` in the DataGridColumn:

<snippet id='datagrid-footercontenttemplate' />

![DataGrid Column Footer Template](../images/footer-content-template.png)

## See Also

- [Text Column]({%slug datagrid-columns-text-column%})
- [Picker Column]({%slug datagrid-columns-picker-column%})
- [Template Column]({%slug datagrid-columns-template-column%})
