---
title: Filter Control Template
page_title: .NET MAUI TreeDataGrid Documentation - Filter Control Template
description: Review the Telerik .NET MAUI TreeDataGrid Filter Control Template documentation article to learn more about applying custom filter to the DataGrid using FilterControlTemplate property.
position: 2
slug: treedatagrid-filter-control-template
---

# Filter Control Template

The [Telerik UI for .NET MAUI TreeDataGrid]({%slug datagrid-overview%}) inherits the filtering from the DataGrid through the Filtering UI which enables the user to quickly filter the displayed data. 

To customize the built-in Filtering UI for a concrete column, use the `FilterControlTemplate` property of the typed columns (text, boolean, numeric, date, time, and picker columns). 

In addition, as the [template column]({%slug treedatagrid-columns-template-column%}) does not provide a default Filtering UI, with the `FilterControlTemplate` property you can allow users to filter data in template columns as well.

* `FilterControlTemplate`(`DataTemplate`)&mdash;Specifies the user defined template used for Filtering UI. The template must contain an instance of the `Telerik.Maui.Controls.DataGrid.DataGridFilterControlBase` class. 

The DataGrid provides the following predefined filter controls which are applied depending on the column type:

* `DataGridTextFilterControl`
* `DataGridNumericFilterControl`
* `DataGridBooleanFilterControl`
* `DataGridDateTimeFilterControl`
* `DataGridTimeFilterControl`
* `DataGridComboBoxFilterControl`

The `FilterControlTemplate` property of the columns allows you to customize its corresponding filter control. If the default filter control does not meet the requirements, you can create a custom filter control from scratch. 

## See Also

- [Columns Overview]({%slug datagrid-columns-overview%})
- [Filtering UI]({%slug datagrid-filtering-ui%})
- [Programmatic Filtering]({%slug datagrid-programmatic-filtering%})
