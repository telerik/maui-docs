---
title: Filtering UI
page_title: .NET MAUI DataGrid Documentation - Filtering UI
description: Check our Filtering UI documentation article for Telerik DataGrid for .NET MAUI control.
position: 0
slug: datagrid-filtering-ui
---

# Filtering

The DataGrid supports filtering through the UI - [Filtering UI](#filtering-ui) and [programmatic filtering](#programmatic-filtering).


# Filtering UI

> On Mobile (iOS and Android) Filtering UI appears when clicking the options icon (**OptionsButton**, three dots) on each column's header and it allows the user to easily filter data by column values.
>
> On Desktop Filtering UI appears when clicking on the filtering icon on each column's header'.

![DataGrid Filtering UI](../images/datagrid-filtering.png)

The Filtering UI exposes the following properties:

* `UserFilterMode`&mdash;Defines whether the Filtering UI is enabled/disabled. The available options are *Auto/Enabled/Disabled*. The default value of the UserFilterMode is *Auto*. Set the property on DataGrid control.

* `CanUserFilter`(`bool`) property is used to enable/disable the filtering of a specific column. Set the property to a specific column.

* `ShowDistinctValuesFilter`(`bool`)&mdash;Defines whether the distinct values are included int he Filering UI. By default the value is true.
  
* `FilterContentTemplate`(`DataTemplate`)&mdash;Defines the content template of the DataGrid Columns Filter and overriding the default template.


Events related to DistinctValuesFilter:

* `DistinctValuesLoading` event&mdash;Occurs when loading the distinct values that will be displayed in the `Telerik.Maui.Controls.Compatibility.DataGrid.DataGridDistinctValuesFilterView`. The `DistinctValuesLoading` event handler receives two parameters:
	* The sender argument, which is of type object, but can be cast to the `RadDataGrid` type.
	* A `DistinctValuesLoadingEventArgs` object, which provides the following properties:
		- `DistinctValues`&mdash; Is a property which specifies a list of values of type `IEnumerable` which are to be displayed in the `DataGridDistinctValuesFilterView`.
		- `Column`&mdash; Is a readonly property of type `DataGridColumn` which gets the column for which the distinct values are being loaded.

## See Also

- [Programmatic filtering]({%slug datagrid-grouping-overview%})
- [Sorting]({%slug datagrid-sorting-overview%})
- [Selection]({%slug datagrid-selection-overview%})