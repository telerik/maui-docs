---
title: Column Footer
page_title: .NET MAUI DataGrid Documentation - Footer
description: Check our &quot;Column Footer&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 2
slug: datagrid-column-footer
---

# Column Footers

The DataGrid allows you to display additional information which applies to the columns in a specific row placed at the bottom of the control. This row consists of individual footer cells for each column.

![Column Footer](../images/column-footer.png)

By default, column footers are hidden and in order to make them visible you have to set the `ShowColumnFooters` property to True.

The following example shows how to define a footer in the DataGrid:



## Setting text in the footer

To define a text inside the footer you have to use the `FooterText` property. The property is per column:

> Note that the footer has to be defined per column otherwise the cell will appear empty.

## Styling 

Use the `FooterStyle` property in order to style the DataGridColumn footer.

Check the [DataGrid Column Footer Styling]({%datagrid-columns-styling%}#footerstyle) topic for more information about the styling options you can use. 

## Custom Footer

You can easily customize the default footer appearance using the `FooterContentTemplate`(`DataTemplate`) property.

Define the `DataTemplate` for the footer:

<snippet id='datagrid-footercontenttemplate-datatemplate' />

Define the `FooterContentTemplate` in the DataGrid:

<snippet id='datagrid-footercontenttemplate' />

![DataGrid Column Footer Template](../images/footer-content-template.png)

## See Also

- [Text Column]({%slug datagrid-columns-text-column %})
- [Picker Column]({%slug datagrid-columns-picker-column %})
- [Template Column]({%slug datagrid-columns-template-column %})
