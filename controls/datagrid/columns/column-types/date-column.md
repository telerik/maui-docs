---
title: Date Column
page_title: .NET MAUI DataGrid Documentation - Date Column
description: Check our &quot;Date Column&quot; documentation article for Telerik DataGrid for .NET MAUI.
position: 3
slug: datagrid-columns-date-column
---

# DataGrid DateColumn

The `DataGridDateColumn` is used to represent `DateTime` objects. It uses the Telerik Ui for .NET MAUI [DatePicker control](%slug datepicker-overview%) to pick a value in EditMode.

## Important Properties

* `PropertyName`&mdash;Specifies the name of the property of the object type that represents each row within the grid.
* `HeaderText`&mdash;Defines the content that will be displayed in the Header UI that represents the column.
* `CellContentStyle`&mdash;Defines the `Style` object that sets the appearance of each cell associated with this column. The `TargetType` of the `Style` has to be of the `TextBlock` type.
* `CellContentStyleSelector`&mdash;Defines the `StyleSelector` instance that allows for the dynamic appearance on a per-cell basis.
* `CellContentFormat`&mdash;Specifies the custom format for each cell value. The `String.Format` routine is used and the format passed has to be in the form required by this method.
* `CellContentTemplate` (`DataTemplate`)&mdash;Defines the appearance of each cell associated with the concrete column. `CellContenTemplate` enables you to customize the default content of the cell.
* `CellEditTemplate` (`DataTemplate`)&mdash;Defines the editor associated with the concrete column. The `CellEditTemplate` is displayed when the cell is in edit mode.

>tip For more information about `CellDecorationStyle` and  `CellDecorationStyleSelector`, refer to the [Columns Styling]({%slug datagrid-columns-styling%}) topic.

>important `CellContentFormat` uses the format string provided by the framework. For more details, refer to the [Standard Date and Time Formatting](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings) and [Custom Date and Time Formatting](https://docs.microsoft.com/en-us/dotnet/standard/base-types/custom-date-and-time-format-strings) articles.

```XAML
<telerik:DataGridDateColumn PropertyName="Established"
                                HeaderText="Date Established"
                                CellContentFormat="{}{0: ddd-d-MMM-yyyy}">
    <telerik:DataGridDateColumn.CellContentStyle>
        <telerik:DataGridTextCellStyle TextColor="LightBlue"
                                           FontSize="18"
                                           SelectedTextColor="Blue" />
    </telerik:DataGridDateColumn.CellContentStyle>
</telerik:DataGridDateColumn>
```

![DataGrid Date Column](images/datecolumn-overview.png)

**Example with CellContenTemplate and CellEditTemplate**

```XAML
<telerik:DataGridDateColumn PropertyName="Established" 
							HeaderText="Date Established">
	<telerik:DataGridColumn.CellContentTemplate>
		<DataTemplate>
			<Label Text="{Binding Established}"/>
		</DataTemplate>
	</telerik:DataGridColumn.CellContentTemplate>
	<telerik:DataGridColumn.CellEditTemplate>
		<DataTemplate>
			<telerik:RadDatePicker Date="{Binding Established}" 
								   DisplayStringFormat="yyyy/MMM/dd"
								   VerticalOptions="Center"/>
		</DataTemplate>
	</telerik:DataGridColumn.CellEditTemplate>
</telerik:DataGridDateColumn>
```

## See Also

- [Columns Styling]({%slug datagrid-columns-styling%})
- [Text Column]({%slug datagrid-columns-text-column%})
- [Time Column]({%slug datagrid-columns-time-column%})
