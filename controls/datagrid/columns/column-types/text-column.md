---
title: Text Column
page_title: .NET MAUI DataGrid Documentation | Text Column
description: Check our &quot;Text Column&quot; documentation article for Telerik DataGrid for .NET MAUI.
position: 0
slug: datagrid-columns-text-column
---

# DataGrid TextColumn

A `DataGridTextColumn` converts the content of each associated cell to a `System.String` object.

>note A `DataGridTextColumn` performs better than a `DataGridTemplateColumn`.

## Important Properties

Here are the specific properties for the Text Columns:

* `PropertyName`&mdash;Specifies the name of the property of the object type that represents each row within the grid.
* `HeaderText`&mdash;Defines the content that will be displayed in the Header UI that represents the column.
* `CellContentFormat`&mdash;Defines the custom format for each cell value. The `String.Format` routine is used and the format passed has to be in the form required by this method.
* `CellContentStyle`&mdash;Defines the `Style` object that sets the appearance of each cell associated with this column.
* `CellContentStyleSelector`&mdash;Defines the `StyleSelector` instance that allows for the dynamic appearance on a per-cell basis.
* `CellContentTemplate` (`DataTemplate`)&mdash;Defines the appearance of each cell associated with the concrete column. `CellContenTemplate` enables you to wrap the text inside each DataGrid column. You can add a Label as a content of the Text and Template Column and wrap its text by using the `LineBreakMode` Label property.
* `CellEditTemplate` (`DataTemplate`)&mdash;Defines the editor associated with the concrete column. The `CellEditTemplate` is displayed when the cell is in edit mode.

>tip For more information about `CellDecorationStyle` and  `CellDecorationStyleSelector`, refer to the [Columns Styling]({%slug datagrid-columns-styling%}) topic.

>important `CellContentFormat` uses the format string provided by the framework. For more details, refer to the [`String.Format`](https://docs.microsoft.com/en-us/dotnet/api/system.string.format?view=netframework-4.8) article.

## Example

Here is an example how the Text Column properties can be used:

```XAML
<telerik:DataGridTextColumn PropertyName="Name"
                            HeaderText="Name"
							CellContentFormat="FC {0}">
	<telerik:DataGridTextColumn.CellContentStyle>
    	<telerik:DataGridTextCellStyle TextColor="Green"
                                       FontSize="15"
                                       SelectedTextColor="Orange"/>
 	</telerik:DataGridTextColumn.CellContentStyle>
 </telerik:DataGridTextColumn>
```

![Text Column](images/textcolumn-overview.png)

## See Also

- [Columns Styling]({%slug datagrid-columns-styling%})
- [Numerical Column]({%slug datagrid-columns-numerical-column%})
- [Boolean Column]({%slug datagrid-columns-boolean-column%})
