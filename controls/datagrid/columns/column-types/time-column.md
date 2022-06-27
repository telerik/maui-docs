---
title: Time Column
page_title: .NET MAUI DataGrid Documentation - Time Column
description: Check our &quot;Time Column&quot; documentation article for Telerik DataGrid for .NET MAUI.
position: 4
slug: datagrid-columns-time-column
---

# DataGrid TimeColumn

The `DataGridTimeColumn` is used to represent `TimeSpan` objects. It uses the Telerik UI for .NET MAUI [TimePicker control]({%slug timepicker-overview%}) to pick a value in EditMode.

## Important Properties

* `PropertyName`&mdash;Specifies the name of the property of the object type that represents each row within the grid.
* `HeaderText`&mdash;Defines the content that will be displayed in the Header UI that represents the column.
* `CellContentStyle`&mdash;Defines the `Style` object that sets the appearance of each cell associated with this column. The `TargetType` of the `Style` has to be of the `TextBlock` type.
* `CellContentStyleSelector`&mdash;Defines the `StyleSelector` instance that allows for the dynamic appearance on a per-cell basis.
* `CellContentFormat`&mdash;Defines the custom format for each cell value. The `String.Format` routine is used and the format passed has to be in the form required by this method.
* `CellContentTemplate` (`DataTemplate`)&mdash;Defines the appearance of each cell associated with the concrete column. `CellContenTemplate` enables you to wrap the text inside each DataGrid column. You can add a Label as a content of the Text and Template Column and wrap its text by using the `LineBreakMode` Label property.
* `CellEditTemplate` (`DataTemplate`)&mdash;Defines the editor associated with the concrete column. The `CellEditTemplate` is displayed when the cell is in edit mode.

>tip For more information about `CellDecorationStyle` and `CellDecorationStyleSelector`, refer to the [Columns Styling]({%slug datagrid-columns-styling%}) topic.

>important `CellContentFormat` uses the format string provided by the framework. For more details, refer to the [Standard Date and Time Formatting](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings) and [Custom Date and Time Formatting](https://docs.microsoft.com/en-us/dotnet/standard/base-types/custom-date-and-time-format-strings) articles.

## Example

```XAML
<telerik:DataGridTimeColumn PropertyName="Time"
                            HeaderText="Time Column"
                            CellContentFormat="{}{0: hh:mm:ss}">
    <telerik:DataGridTimeColumn.CellContentStyle>
        <telerik:DataGridTextCellStyle TextColor="Lime"
                                       FontSize="18"
                                       SelectedTextColor="Red" />
    </telerik:DataGridTimeColumn.CellContentStyle>
</telerik:DataGridTimeColumn>
```

![Time Column](images/timecolumn-overview.png)

## See Also

- [Columns Styling]({%slug datagrid-columns-styling%})
- [Text Column]({%slug datagrid-columns-text-column%})
- [Date Column]({%slug datagrid-columns-date-column%})
