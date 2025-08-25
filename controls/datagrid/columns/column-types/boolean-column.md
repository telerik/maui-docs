---
title: Boolean Column
page_title: .NET MAUI DataGrid Documentation - Boolean Column
description: Check our &quot;Boolean Column&quot; documentation article for Telerik DataGrid for .NET MAUI.
position: 2
slug: datagrid-columns-boolean-column
---

# .NET MAUI DataGrid BooleanColumn

The `DataGridBooleanColumn` is used to represent boolean values. It uses the CheckBox control to edit its values in `EditMode`.

## Important Properties

* `PropertyName`&mdash;Specifies the name of the property of the object type that represents each row within the grid.
* `DataMemberBinding`&mdash;Defines the binding which points to the data member of the underlying object being displayed in the column's cell.
* `HeaderText`&mdash;Defines the content that will be displayed in the Header UI that represents the column.
* `CellContentStyle`(`DataGridTextCellStyle`)&mdash;Defines the appearance of each cell associated with this column. 
* `CellContentStyleSelector`&mdash;Defines the `StyleSelector` instance that allows for the dynamic appearance on a per-cell basis.
* `CellContentFormat`&mdash;Defines the custom format for each cell value. The `String.Format` routine is used and the format passed has to be in the form required by this method.
* `CellContentTemplate`(`DataTemplate`)&mdash;Defines the appearance of each cell associated with the concrete column. The `CellContentTemplate` enables you to customize the default content of the cell.
* `CellContentTemplateSelector` (`DataTemplateSelector`)&mdash;Defines a `DataTemplateSelector` instance that may be used to retrieve dynamic data templates on a per-cell basis.
* `CellEditTemplate`(`DataTemplate`)&mdash;Defines the editor associated with the concrete column. The `CellEditTemplate` is displayed when the cell is in edit mode.
* `FooterText`&mdash;Defines the content that will be displayed in the Footer UI that represents the column.
* `FooterStyle`(`DataGridColumnFooterStyle`)&mdash;Defines the `Style` object that sets the appearance of each footer cell associated with this column.
* `FooterContentTemplate`(`DataTemplate`)&mdash;Defines the appearance of the footer.
* `IsResizable`(`bool`)&mdash;Specifies whether the user can resize the DataGrid Column. The default value is `True`.This is only supported in `WinUI` and `MacCatalyst`.
* `IsFrozen`(`bool`)&mdash;Specifies whether the column is frozen. The default value is `False`.
* `DataGrid`(`RadDataGrid`)&mdash;Gets the corresponding `RadDataGrid` control.

>tip For more information about `CellDecorationStyle` and  `CellDecorationStyleSelector`, refer to the [Columns Styling]({%slug datagrid-columns-styling%}) topic.

>important `CellContentFormat` uses the format string provided by the framework. For more details, refer to the [`String.Format`](https://docs.microsoft.com/en-us/dotnet/api/system.string.format?view=netframework-4.8) article.

```XAML
<telerik:DataGridBooleanColumn PropertyName="IsChampion"
                               HeaderText="Champion?">
    <telerik:DataGridBooleanColumn.CellContentStyle>
        <telerik:DataGridTextCellStyle TextColor="Green"
                                       FontSize="18"
                                       SelectedTextColor="Blue" />
    </telerik:DataGridBooleanColumn.CellContentStyle>
</telerik:DataGridBooleanColumn>
```

![DataGrid Boolean Column](images/booleancolumn-overview.png)

**Example with CellContentTemplate and CellEditTemplate**

```XAML
<telerik:DataGridBooleanColumn PropertyName="IsChampion" 
							   HeaderText="Champion?">
	<telerik:DataGridColumn.CellContentTemplate>
		<DataTemplate>
			<Label Text="{Binding IsChampion}"/>
		</DataTemplate>
	</telerik:DataGridColumn.CellContentTemplate>
	<telerik:DataGridColumn.CellEditTemplate>
		<DataTemplate>
			<Switch IsToggled="{Binding IsChampion}"
					VerticalOptions="Center"/>
		</DataTemplate>
	</telerik:DataGridColumn.CellEditTemplate>
</telerik:DataGridBooleanColumn>
```

## See Also

- [Columns Styling]({%slug datagrid-columns-styling%})
- [Text Column]({%slug datagrid-columns-text-column%})
- [Numerical Column]({%slug datagrid-columns-numerical-column%})
