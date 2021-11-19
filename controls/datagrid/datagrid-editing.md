---
title: Editing
page_title: .NET MAUI DataGrid Documentation | Editing
description: Check our &quot;Editing&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 4
slug: datagrid-editing
---

# Editing

The DataGrid provides a built-in editing functionality, which allows the app users to easily edit the data presented in the Grid. Depending on the column data type, a relevant editor allows end users to edit content in a friendly environment. As soon as the user double-clicks on a certain cell, the cell is switched to an edit mode.

## Important Properties

You need to define the `UserEditMode` property of the DataGrid control to enable the editing feature.

The `UserEditMode` property is of type `Telerik.XamarinForms.DataGrid.DataGridUserEditMode` and accepts the following values:

* (Default) `None`&mdash;Editing is disabled.
* `Cell`&mdash;Enables the editing option.

In addition, you can independently disable editing for specific columns through the `CanUserEdit` property of the `DataGridColumn` class. For more details, refer to the [Columns Overview]({%slug datagrid-columns-overview%}) topic.

## Column Editors

Each DataGrid column type provides different editor, so that the content can be edited in a convenient manner according to its value type.

The following table lists the related .NET MAUI control for editing the values inside the DataGrid columns:

| Column Type 		| Editor 			|
|-------------------|-------------------|
| `TextColumn`		| Entry				|
| `NumericalColumn`	| Entry				|
| `BooleanColumn`		| Switch			|
| `DateColumn`		| DatePicker		|
| `TimeColumn`		| TimePicker		|
| `PickerColumn`		| Picker			|
| `TemplateColumn`	| A custom editor by defining `CellEditTemplate`. |

## CellEditTemplate

If the default editors do not suit the scenario you have, create a custom editor for each column by utilizing the `CellEditTemplate` property of the `DataGridColumn`. For detailed information on how the `CellEditTemplate` can be applied, refer to the [Columns Cell Templates]({%slug datagrid-cell-templates%}) article.

## Editing Commands

The DataGrid provides a few useful commands related to the editing functionality, such as:

* `BeginEdit`&mdash;Provides an entry point just before the editing begins.
* `CancelEdit`&mdash;Provides an entry point just before the editing is canceled.
* `CommitEdit`&mdash;Provides an entry point just before the editing is committed.

For detailed information on how to utilize any of the listed commands, go to the [Editing Commands]({%slug datagrid-commands-editing%}) topic.

## Styling

You can change the visual appearance of each editor through the `CellEditorStyle` property of the `DataGridColumn`. To the `CellEditorStyle` you will need to apply a `Xamarin.Forms.Style` with a `TargetType` set to the corresponding to each column editor control.

The following snippet shows a `CellEditorStyle` applied to the `DataGridTextColumn`:

<snippet id='datagrid-columnstyle-celleditor'/>
```XAML
<telerikDataGrid:DataGridTextColumn.CellEditorStyle>
    <Style TargetType="Entry">
        <Setter Property="FontSize" Value="Large"/>
        <Setter Property="FontAttributes" Value="Bold"/>
    </Style>
</telerikDataGrid:DataGridTextColumn.CellEditorStyle>
```

## See Also

- [Editing Commands]({%slug datagrid-commands-editing%})
- [Columns Cell Templates]({%slug datagrid-cell-templates%})
- [Columns Styling]({%slug datagrid-columns-styling%})
