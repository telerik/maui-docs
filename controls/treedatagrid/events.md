---
title: Events
page_title: .NET MAUI TreeDataGrid Documentation - Events
description: Learn about the Telerik UI for .NET MAUI TreeDataGrid events and how to achieve various scenarios upon user interaction such as loading content on demand, binding to data, and more.
position: 14
tags: events
slug: treedatagrid-events
---

# .NET MAUI TreeDataGrid Events

The [Telerik UI for .NET MAUI TreeDataGrid]({%slug datagrid-overview%}) component inherits the events from the [DataGrid]({%slug datagrid-overview%}) control a set of events which help users achieve seamless and effective experience when interacting with the component.

## Loading Content on Demand

The load-on-demand feature gets implemented through the `LoadOnDemand` event. The `LoadOnDemand` event handler receives the following parameters:
* The `sender` argument, which is of type `object`, but can be cast to the `RadDataGrid` type.
* A `LoadOnDemandEventArgs` object, which provides the `IsDataLoaded` (`bool`) property, indicating whether the data is loaded.

For more information, see the topic about [loading data on demand in the .NET MAUI TreeDataGrid]({%slug datagrid-features-loadondemand%}).

## Loading Distinct Values

The TreeDataGrid enables you to load the distinct values that will be displayed in the `Telerik.Maui.Controls.DataGrid.DataGridDistinctValuesFilterView` through the `DistinctValuesLoading` event. The `DistinctValuesLoading` event handler receives the following parameters:

* The `sender` argument, which is of type `object`, but can be cast to the `RadDataGrid` type.
* A `DistinctValuesLoadingEventArgs` object, which provides the following properties:
	- `DistinctValues`&mdash;Specifies a list of values of type `IEnumerable` which are to be displayed in the `DataGridDistinctValuesFilterView`.
	- (Read-only) `Column` of type `DataGridColumn`&mdash;Gets the column for which the distinct values are being loaded.

For more information, see the topic about the [available filtering options in the .NET MAUI TreeDataGrid]({%slug treedatagrid-filtering-overview%}).

## Binding to Data

The TreeDataGrid also gives you the option to use the `DataBindingComplete` event which occurs when the associated TreeDataGrid `ItemsSource` has been successfully bound to the control, or when any data operation like grouping, sorting, or filtering is applied. The `DataBindingComplete` event handler receives the following parameters:

* The `sender` argument, which is of type `object`, but can be cast to the `RadDataGrid` type.
* A `DataBindingCompleteEventArgs` object, which provides the `DataView` (`IDataViewCollection`) property and allows for traversing and/or manipulating the already computed data view.

## Modifying the Selection

The TreeDataGrid inherits the `SelectionChanged` event which is triggered whenever the `SelectedItems` collection is changed. The `SelectionChanged` event handler receives the following parameters:
* The `sender` argument, which is of type `object`, but can be cast to the `RadDataGrid` type.
* A `DataGridSelectionChangedEventArgs` object, which provides the following properties:
	- `RemovedItems`&mdash;Gets a list of the removed items from the `SelectedItems` collection.
	- `AddedItems`&mdash;Gets a list of the added items to the `SelectedItems` collection.

For more information, see the article about the [`SelectionChanged` event of the .NET MAUI TreeDataGrid]({%slug treedatagrid-selection-overview%}).

## Changing the Current Cell

The TreeDataGrid also supports the `CurrentCellChanged` event which is invoked when the current cell changes. The `CurrentCellChanged` event handler receives the following parameters:

* The `sender` argument, which is of type `object`, but can be cast to the `RadDataGrid` type.
* A `CurrentCellChangedEventArgs` object, which provides the following properties:
	- `OldCurrentCell`&mdash;Gets the previously `CurrentCell`.
	- `NewCurrentCell`&mdash;Gets the new `CurrentCell`.

For more information, see the article about the [`CurrentCellChanged` event in the .NET MAUI TreeDataGrid]({%slug treedatagrid-current-cell%}).

## Reordering the Column

The TreeDataGrid inherits the `ColumnReorderStarting`, `ColumnReordering`, `ColumnReorderCompleting`, and `ColumnReordered` events related to the column reordering operation. For more details, review the TreeDataGrid [Columns Reordering]({%slug treedatagrid-columns-reordering%}#events) article. 

## Resizing the Column

The TreeDataGrid resizing feature exposes a `ColumnUserResizeCompleted` event which is invoked when a column is resized by user interaction. The `ColumnUserResizeCompleted` event handler receives the following parameters:
* The `sender` argument, which is of type `object`, but can be cast to the `RadDataGrid` type.
* A `ColumnUserResizeCompletedEventArgs` object, which provides the following properties:
	- `Column` (`DataGridColumn`)&mdash;Gets the previously `CurrentCell`.
	- `Width` (`double`)&mdash;Gets the width of the column that is resized.

## Additional Resources

- [.NET MAUI TreeDataGrid Product Page](https://www.telerik.com/maui-ui/treedatagrid)
- [.NET MAUI TreeDataGrid Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Setting the .NET MAUI TreeDataGrid Columns]({%slug treedatagrid-columns-overview%})