---
title: Editing
page_title: .NET MAUI DataGrid Documentation - Editing
description: "Learn how to use the built-in column and custom editors for modifying the data records in the Telerik UI for .NET MAUI DataGrid component."
position: 9
previous_url: /controls/datagrid/datagrid-editing
slug: datagrid-editing
---

# .NET MAUI DataGrid Editing

The [Telerik UI for .NET MAUI DataGrid]({%slug datagrid-overview%}) provides built-in editing capabilities, which allow users to modify the data presented in the Grid.

Depending on the [DataGrid column data type]({% slug datagrid-columns-boolean-column %}), the DataGrid provides a relevant editor which allows users to edit the content upon double-clicking the desired cell.

## Editing Properties

To enable editing in the DataGrid, define the `UserEditMode` property of the component. `UserEditMode` is of type `Telerik.Maui.Controls.DataGrid.DataGridUserEditMode` and accepts the following values:

* `None`&mdash;(default on Mobile) Editing is disabled.
* `Cell`&mdash;(default on Desktop) Enables the editing option.

You can also independently disable editing for specific columns through the `CanUserEdit` property of the `DataGridColumn` class. For more details, refer to the topic about [columns in the .NET MAUI DataGrid]({%slug datagrid-columns-overview%}).

## Column Editors

Each DataGrid column type provides different editor, so that the content can be edited in a convenient manner according to its value type.

The following table lists the integrated .NET MAUI control for editing the values inside the DataGrid columns:

| Column Type 		| Editor 			|
|-------------------|-------------------|
| `TextColumn`		| Entry				|
| `NumericalColumn`	| RadNumericInput	|
| `BooleanColumn`	| CheckBox		    |
| `DateColumn`		| RadDatePicker		|
| `TimeColumn`		| RadTimePicker		|
| `PickerColumn`	| RadComboBox	    |
| `TemplateColumn`	| A custom editor by defining `CellEditTemplate`. |

## Custom Editors

If the default editors do not suit the scenario you have, create a custom editor for each column by utilizing the `CellEditTemplate` property of the `DataGridColumn`. For detailed information on how the `CellEditTemplate` can be applied, refer to the article about the [.NET MAUI DataGrid column cell templates]({%slug datagrid-cell-templates%}).

## Editing Commands

The DataGrid provides the following commands related to the editing functionality:

* `BeginEdit`&mdash;Provides an entry point just before the editing begins.
* `CancelEdit`&mdash;Provides an entry point just before the editing is canceled.
* `CommitEdit`&mdash;Provides an entry point just before the editing is committed.

For detailed information on how to use any of the listed commands, go to the topic about the [.NET MAUI DataGrid editing commands]({%slug datagrid-commands-editing%}).

## Styling

You can change the visual appearance of each editor through the `CellEditorStyle` property of the `DataGridColumn`. To the `CellEditorStyle`, apply a `Microsoft.Maui.Controls.Style` with a `TargetType` set to the corresponding to each column editor control.

The following snippet shows a `CellEditorStyle` applied to the `DataGridTextColumn`.

<snippet id='datagrid-columnstyle-celleditor'/>

## Additional Resources

- [.NET MAUI DataGrid Product Page](https://www.telerik.com/maui-ui/datagrid)
- [.NET MAUI DataGrid Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Editing Commands in the Telerik UI for .NET MAUI DataGrid]({%slug datagrid-commands-editing%})
- [Column Cell Templates in the .NET MAUI DataGrid]({%slug datagrid-cell-templates%})
- [Styling the Columns of the .NET MAUI DataGrid]({%slug datagrid-columns-styling%})

