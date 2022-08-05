---
title: Footer
page_title: .NET MAUI DataGrid Documentation - Footer
description: Check our &quot;Sorting&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 1
slug: datagrid-footer-overview
---

# Column Footers

The DataGrid allows you to display additional information which applies to the columns in a specific row placed at the bottom of the control. This row consists of individual footer cells for each column.

By default, column footers are hidden and in order to make them visible you have to set the ShowColumnFooters property to True.

## Footer Example

The following example shows how to define a footer in the DataGrid&mdash;

```XAML
<telerik:RadDataGrid x:Name="dataGrid" 
                     ShowColumnFooters="True"/>
```

To set the value of the footer cells, you can use the Footer property when defining the columns&mdash;
```XAML
<telerik:DataGridTextColumn PropertyName="Name" 
                            FooterText="Footer Cell"
                            HeaderText="Name">
```

> Note that the footer content needs to be defined for every column otherwise the cell will appear empty.


## Properties

The DataGrid footer comes with its certain set of properties. The following API has been provided&mdash;

| Name 		              | Class 			 | Type 					  | Default value |
|-------------------------|------------------|----------------------------|---------------|
| `ShowColumnFooters`	  | `RadDataGrid` 	 | `Bool` 					  | `false`		  |
| `FooterText` 			  | `DataGridColumn` | `String` 				  | `null` 		  |
| `FooterStyle`    		  | `DataGridColumn` | `DataGridColumnFooterStyle`| `null` 		  |
| `FooterContentTemplate` | `DataGridColumn` | `DataTemplate` 			  | `null` 		  |


* `ShowColumnFooters`&mdash;Gets or sets a value indicating whether to show column footers.
* `FooterText`&mdash;Gets or sets the content to be displayed in the Footer UI of the Column.
* `FooterStyle`&mdash;Gets or sets the `DataGridColumnFooterStyle` instance that defines the appearance of the DataGridColumn footer.
* `FooterContentTemplate`&mdash;Gets or sets the DataTemplate instance that defines the appearance of the footer.

More information about `DataGridColumnFooterStyle` you can find on the following link&mdash; ({%datagrid-columns-styling%})

## See Also

- [Text Column]({%slug datagrid-columns-text-column %})
- [Picker Column]({%slug datagrid-columns-picker-column %})
- [Template Column]({%slug datagrid-columns-template-column %})
