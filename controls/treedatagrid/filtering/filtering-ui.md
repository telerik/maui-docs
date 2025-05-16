---
title: Filtering UI
page_title: .NET MAUI TreeDataGrid Documentation - Filtering UI
description: Review the Telerik .NET MAUI TreeDataGrid Filtering UI documentation article to learn more about the built in Filtering UI functions you can use.
position: 1
slug: treedatagrid-filtering-ui
---

# Filtering UI

The [.NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) provides you with a built-in filtering functionality, which allows the user to filter the data by one or more columns by clicking on the filtering icon next to the header text.

> The Filtering UI appears when the user clicks the filtering icon in a column's header.

You can control whether the Filtering UI is available to the end users for the whole DataGrid with the `UserFilterMode` property:

* `UserFilterMode`(`DataGridUserFilterMode`)&mdash;Defines whether the filtering icon is present in the header of the currently available filterable columns. The available options are `Auto`, `Enabled`, and `Disabled`. The default value of the `UserFilterMode` is `Auto`.

The DataGrid columns expose the following properties related to the Filtering UI: 

* `CanUserFilter`(`bool`)&mdash;Indicates whether the user can filter this column by using the built-in Filtering UI. By default, the value is `True`.

* `ShowDistinctValuesFilter`(`bool`)&mdash;Defines whether the distinct values are included in the Filtering UI. By default, the value is `True`.

* `FilterContentTemplate`(`DataTemplate`)&mdash;Defines the content template of the DataGrid Columns Filter and overriding the default template.

The following events are related to `DistinctValuesFilter`:

* `DistinctValuesLoading` event&mdash;Occurs when loading the distinct values that will be displayed in the `Telerik.Maui.Controls.DataGrid.DataGridDistinctValuesFilterView`. The `DistinctValuesLoading` event handler receives two parameters:
	* The sender argument, which is of type object, but can be cast to the `RadDataGrid` type.
	* A `DistinctValuesLoadingEventArgs` object, which provides the following properties:
		- `DistinctValues`&mdash;Is a property which specifies a list of values of type `IEnumerable` which are to be displayed in the `DataGridDistinctValuesFilterView`.
		- `Column`&mdash;Is a readonly property of type `DataGridColumn` which gets the column for which the distinct values are being loaded.

## See Also

- [Columns Overview]({%slug treedatagrid-columns-overview%})
- [Filter Control Template]({%slug treedatagrid-filter-control-template%})
- [Programmatic Filtering]({%slug treedatagrid-programmatic-filtering%})

