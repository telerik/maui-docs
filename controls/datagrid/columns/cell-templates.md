---
title: Columns Cell Templates
page_title: .NET MAUI DataGrid Documentation - Columns Cell Templates
description: Check our &quot;Columns CellTemplates&quot; documentation article for Telerik DataGrid for .NET MAUI.
position: 2
previous_url: /controls/datagrid/columns/datagrid-columns-cell-templates
slug: datagrid-cell-templates
---

# Columns Cell Templates

This article describes how to set the content and edit templates to the DataGrid column using the `CellContentTemplate` and `CellEditTemplate` properties.

* `CellContentTemplate` (DataTemplate): Defines the appearance of each cell associated with the concrete column. CellContenTemplate gives you the opportunity to wrap the text inside each datagrid column. You can add a Label as a content of the Text, Template Column and wrap its text using the Label's `LineBreakMode` property.
* `CellEditTemplate` (DataTemplate): Defines the editor associated with the concrete column. The CellEditTemplate is displayed when the cell is in edit mode.

## Cell Content Template Example

1. Use the following snippet to declare a RadDataGrid in XAML:

 <snippet id='datagrid-columns-cellcontenttemplate-xaml' />

1. And add the following namespaces:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

1. The `ViewModel` class is declared as following:

 <snippet id='datagrid-column-view-model' />

1. And the `Club` custom object:

 <snippet id='datagrid-club-model' />

DataGrid Date Column with CellContentTemplate property and inside the template we have added a DateTime Picker control

![DataGrid Cell Content Template Property](../images/datagrid-column-cell-content-template.png)

## Cell Edit Template Example

1. Use the following snippet to declare a RadDataGrid in XAML:

 <snippet id='datagrid-columns-celledittemplate-xaml' />

1. And add the following namespaces

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

1. The `ViewModel` class is declared as following:

 <snippet id='datagrid-column-view-model' />

1. And the `Club` custom object:

 <snippet id='datagrid-club-model' />

DataGrid Boolean Column with CellEditTemplate property and inside the template we have added a switch, and two buttons. The edit template is visualized when the cell is in edit mode.

![DataGrid Cell Content Template Property](../images/datagrid-column-cell-edit-template.png)

## See Also

- [ComboBox Column]({%slug datagrid-columns-picker-column %})
- [Template Column]({%slug datagrid-columns-template-column %})
- [Text Column]({%slug datagrid-columns-text-column %})
