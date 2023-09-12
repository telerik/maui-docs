---
title: Columns Cell Templates
page_title: .NET MAUI DataGrid Documentation - Columns Cell Templates
description: Learn how to define cell templates in DataGrid for .NET MAUI columns.
position: 2
previous_url: /controls/datagrid/columns/datagrid-columns-cell-templates
slug: datagrid-cell-templates
---

# .NET MAUI DataGrid Columns Cell Templates

This article describes how to extend the functionality of a DataGrid column and define custom content and edit templates using the `CellContentTemplate` and `CellEditTemplate` properties.

* `CellContentTemplate` (DataTemplate): Defines the appearance of each cell associated with the concrete column. `CellContentTemplate` gives you the opportunity to wrap the text inside each DataGrid column. You can add a Label as a content of the Text, Template Column and wrap its text using the Label's `LineBreakMode` property.
* `CellEditTemplate` (DataTemplate): Defines the editor associated with the concrete column. The `CellEditTemplate` is displayed when the cell is in edit mode.

## Cell Content Template Example

The following example demonstrates how to use the `CellContentTemplate` property to customize your columns. We set a `RadDateTimePicker` as a `CellContentTemplate` for the DataGrid Date Column (Date Established) and a Switch - for the DataGrid Boolean Column (Champion).

**1.** Use the following snippet to declare a `RadDataGrid` in XAML:

<snippet id='datagrid-columns-cellcontenttemplate-xaml' />

**2.** Add the following namespaces:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Declare the `ViewModel` class:

<snippet id='datagrid-column-view-model' />

**4.** And the `Club` custom object:

<snippet id='datagrid-club-model' />

![DataGrid Cell Content Template](../images/datagrid-column-cell-content-template.png)

## Cell Edit Template Example

The following example demonstrates how to use the `CellEditTemplate` property to customize your columns. Here, for the DataGrid Boolean Column (Champion) we set a `CellEditTemplate` containing a Switch and two Buttons for confirming or canceling the edit operation. The edit template is visualized when the cell is in edit mode.

**1.** Use the following snippet to declare a `RadDataGrid` in XAML:

<snippet id='datagrid-columns-celledittemplate-xaml' />

**2.** Add the following namespaces:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Declare the `ViewModel` class:

<snippet id='datagrid-column-view-model' />

**4.** And the `Club` custom object:

 <snippet id='datagrid-club-model' />

![DataGrid Cell Edit Template](../images/datagrid-column-cell-edit-template.png)

## See Also

- [ComboBox Column]({%slug datagrid-columns-picker-column %})
- [Template Column]({%slug datagrid-columns-template-column %})
- [Text Column]({%slug datagrid-columns-text-column %})
