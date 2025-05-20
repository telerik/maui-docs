---
title: Editing
page_title: .NET MAUI TreeTreeDataGrid Documentation - Editing
description: Learn how to use the built-in column and custom editors for modifying the data records in the Telerik UI for .NET MAUI TreeTreeDataGrid component.
position: 11
slug: treedatagrid-editing
---

# .NET MAUI TreeDataGrid Editing

The [Telerik UI for .NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) provides built-in editing capabilities, which allow users to modify the data presented in the Grid.

Depending on the [TreeDataGrid column data type]({% slug treedatagrid-columns-overview%}), the TreeDataGrid provides a relevant editor which allows users to edit the content upon double-clicking the desired cell.

## Editing Properties

To enable editing in the TreeDataGrid, define the `UserEditMode` property of the component. `UserEditMode` is of type `Telerik.Maui.Controls.DataGrid.DataGridUserEditMode` and accepts the following values:

* `None`&mdash;(default on Mobile) Editing is disabled.
* `Cell`&mdash;(default on Desktop) Enables the editing option.

You can also independently disable editing for specific columns through the `CanUserEdit` property of the `TreeDataGridColumn` class. For more details, refer to the topic about [columns in the .NET MAUI TreeDataGrid]({%slug treedatagrid-columns-overview%}).

## Column Editors

Each TreeDataGrid column type provides different editor, so that the content can be edited in a convenient manner according to its value type.

The following table lists the integrated .NET MAUI control for editing the values inside the TreeDataGrid columns:

| Column Type 		| Editor 			|
|-------------------|-------------------|
| `TextColumn`		| `RadEntry`		|
| `NumericalColumn`	| `RadNumericInput`	|
| `BooleanColumn`	| `RadCheckBox`		|
| `DateColumn`		| `RadDatePicker`	|
| `TimeColumn`		| `RadTimePicker`	|
| `PickerColumn`	| `RadComboBox`	    |
| `TemplateColumn`	| A custom editor by defining `CellEditTemplate`. |

## Custom Editors

If the default editors do not suit the scenario you have, create a custom editor for each column by utilizing the `CellEditTemplate` property of the `TreeDataGridColumn`. For detailed information on how the `CellEditTemplate` can be applied, refer to the article about the [.NET MAUI TreeDataGrid column cell templates]({%slug treedatagrid-cell-templates%}).

## Editing Commands

The TreeDataGrid provides the following commands related to the editing functionality:

* `BeginEdit`&mdash;Provides an entry point just before the editing begins.
* `CancelEdit`&mdash;Provides an entry point just before the editing is canceled.
* `CommitEdit`&mdash;Provides an entry point just before the editing is committed.

For detailed information on how to use any of the listed commands, go to the topic about the [.NET MAUI TreeDataGrid editing commands]({%slug treedatagrid-commands-editing%}).

## Styling

You can change the visual appearance of each editor through the `CellEditorStyle` property of the `DataGridColumn`. To the `CellEditorStyle`, apply a `Microsoft.Maui.Controls.Style` with a `TargetType` set to the corresponding to each column editor control.

The following snippet shows a `CellEditorStyle` applied to the `TreeDataGridTextColumn`.

<snippet id='TreeDataGrid-columnstyle-celleditor'/>

## Additional Resources

- [.NET MAUI TreeDataGrid Product Page](https://www.telerik.com/maui-ui/TreeDataGrid)
- [.NET MAUI TreeDataGrid Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Editing Commands in the Telerik UI for .NET MAUI TreeDataGrid]({%slug treedatagrid-commands-editing%})
- [Column Cell Templates in the .NET MAUI TreeDataGrid]({%slug treedatagrid-cell-templates%})
