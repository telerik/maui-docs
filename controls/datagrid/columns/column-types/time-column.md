---
title: Time Column
page_title: .NET MAUI DataGrid Documentation - Time Column
description: Check our &quot;Time Column&quot; documentation article for Telerik DataGrid for .NET MAUI.
position: 4
slug: datagrid-columns-time-column
---

# .NET MAUI DataGrid TimeColumn

The `DataGridTimeColumn` is used to represent `TimeSpan` objects. It uses the Telerik UI for .NET MAUI [TimePicker control]({%slug timepicker-overview%}) to pick a value in `EditMode`.

## Important Properties

* `PropertyName`&mdash;Specifies the name of the property of the object type that represents each row within the grid.
* `DataMemberBinding`&mdash;Defines the binding which points to the data member of the underlying object being displayed in the column's cell.
* `HeaderText`&mdash;Defines the content that will be displayed in the Header UI that represents the column.
* `CellContentStyle`(`DataGridTextCellStyle`)&mdash;Defines the appearance of each cell associated with this column. 
* `CellContentStyleSelector`&mdash;Defines the `StyleSelector` instance that allows for the dynamic appearance on a per-cell basis.
* `CellContentFormat`&mdash;Defines the custom format for each cell value. The `String.Format` routine is used and the format passed has to be in the form required by this method.
* `CellContentTemplate` (`DataTemplate`)&mdash;Defines the appearance of each cell associated with the concrete column. `CellContentTemplate` enables you to customize the default content of the cell.
* `CellContentTemplateSelector` (`DataTemplateSelector`)&mdash;Defines a `DataTemplateSelector` instance that may be used to retrieve dynamic data templates on a per-cell basis.
* `CellEditTemplate` (`DataTemplate`)&mdash;Defines the editor associated with the concrete column. The `CellEditTemplate` is displayed when the cell is in edit mode.
* `FooterText`&mdash;Defines the content that will be displayed in the Footer UI that represents the column.
* `FooterStyle` (`DataGridColumnFooterStyle`)&mdash;Defines the `Style` object that sets the appearance of each footer cell associated with this column.
* `FooterContentTemplate` (`DataTemplate`)&mdash;Defines the appearance of the footer.
* `IsResizable`(`bool`)&mdash;Specifies whether the user can resize the DataGrid Column. The default value is `True`.This is only supported in `WinUI` and `MacCatalyst`.
* `IsFrozen`(`bool`)&mdash;Specifies whether the column is frozen. The default value is `False`.
* `DataGrid`(`RadDataGrid`)&mdash;Gets the corresponding `RadDataGrid` control.

> For more information about `CellContentStyle` and `CellDecorationStyle` refer to the [Columns Styling]({%slug datagrid-columns-styling%}) topic.
> 
> For `CellContentStyleSelector` and `CellDecorationStyleSelector`, refer to the [Style Selectors]({%slug datagrid-style-selectors%}) topic.

>important `CellContentFormat` uses the format string provided by the framework. For more details, refer to the [Standard Date and Time Formatting](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings) and [Custom Date and Time Formatting](https://docs.microsoft.com/en-us/dotnet/standard/base-types/custom-date-and-time-format-strings) articles.

Examples with `CellContentFormat`:

```XAML
<telerik:DataGridTimeColumn PropertyName="Time"
                            HeaderText="Time Column"
                            CellContentFormat="{}{0:hh\:mm\:ss}" />
```
```XAML
<telerik:DataGridTimeColumn PropertyName="Time" 
                            HeaderText="Time Column"
                            CellContentFormat="{}{0:mm}:{0:ss}" />
```
```C#
this.dataGrid.Columns.Add(new DataGridTimeColumn
{
    PropertyName = "Time",
    CellContentFormat = "{0:hh\\:mm\\:ss}"
});
```

![DataGrid Time Column](images/timecolumn-overview.png)

**Example with CellContentTemplate and CellEditTemplate**

```XAML
<telerik:DataGridTimeColumn PropertyName="Time" 
							HeaderText="Time">
	<telerik:DataGridColumn.CellContentTemplate>
		<DataTemplate>
			<Label Text="{Binding Time}"/>
		</DataTemplate>
	</telerik:DataGridColumn.CellContentTemplate>
	<telerik:DataGridColumn.CellEditTemplate>
		<DataTemplate>
			<telerik:RadTimePicker Time="{Binding Time}"/>
		</DataTemplate>
	</telerik:DataGridColumn.CellEditTemplate>
</telerik:DataGridDateColumn>
```

## See Also

- [Columns Styling]({%slug datagrid-columns-styling%})
- [Text Column]({%slug datagrid-columns-text-column%})
- [Date Column]({%slug datagrid-columns-date-column%})
