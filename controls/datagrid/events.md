---
title: Events
page_title: .NET MAUI DataGrid Documentation - Events
description: Learn about the Telerik UI for .NET MAUI DataGrid events and how to handle user interactions and data operations like loading, binding, and grouping.
position: 17
tags: events
slug: datagrid-events
---

# .NET MAUI DataGrid Events

The [Telerik UI for .NET MAUI DataGrid]({%slug datagrid-overview%}) component exposes a set of events which help users achieve seamless and effective experience when interacting with the component.

## Finished Content Painting

The `ContentPaintCompleted` event is raised when the DataGrid has arranged its content and finished painting. The `ContentPaintCompleted` event handler receives the following parameters:

* The `sender` argument, which is of type `object`, but can be cast to the `RadDataGrid` type.
* A `DataGridContentPaintCompletedEventArgs` object, which allows you to get the information whether the painted content of the data grid is frozen by the `IsContentFrozen` (`bool`) property.

## Loading Content on Demand

The load-on-demand feature gets implemented through the `LoadOnDemand` event. The `LoadOnDemand` event handler receives the following parameters:
* The `sender` argument, which is of type `object`, but can be cast to the `RadDataGrid` type.
* A `LoadOnDemandEventArgs` object, which provides the `IsDataLoaded` (`bool`) property, indicating whether the data is loaded.

For more information, see the topic about [loading data on demand in the .NET MAUI DataGrid]({%slug datagrid-features-loadondemand%}).

The following example demonstrates how to use the `LoadOnDemand` event.

**1.** Define the `LoadOnDemand` method in XAML.

<snippet id='datagrid-loadondemand-event-xaml'/>

**2.** Create the method that defines the functionality of the event.

<snippet id='datagrid-loadondemand-event-csharp'/>

## Loading Distinct Values

The DataGrid enables you to load the distinct values that will be displayed in the `Telerik.Maui.Controls.DataGrid.DataGridDistinctValuesFilterView` through the `DistinctValuesLoading` event. The `DistinctValuesLoading` event handler receives the following parameters:

* The `sender` argument, which is of type `object`, but can be cast to the `RadDataGrid` type.
* A `DistinctValuesLoadingEventArgs` object, which provides the following properties:
	- `DistinctValues`&mdash;Specifies a list of values of type `IEnumerable` which are to be displayed in the `DataGridDistinctValuesFilterView`.
	- (Read-only) `Column` of type `DataGridColumn`&mdash;Gets the column for which the distinct values are being loaded.

For more information, see the topic about the [available filtering options in the .NET MAUI DataGrid]({%slug datagrid-filtering-overview%}).

## Binding to Data

The DataGrid also provides the `DataBindingComplete` event which occurs when the associated DataGrid `ItemsSource` has been successfully bound to the control, or when any data operation like grouping, sorting, or filtering is applied. The `DataBindingComplete` event handler receives the following parameters:

* The `sender` argument, which is of type `object`, but can be cast to the `RadDataGrid` type.
* A `DataBindingCompleteEventArgs` object, which provides the following properties: 
	* `DataView` (`IDataViewCollection`) property&mdash;Allows for traversing and/or manipulating the already computed data view.
	* `ChangeFlags` (`enum` of type `DataChangeFlags`)&mdash;Specifies the type of change that has occurred in the data view. The possible values are:
		- `None`&mdash;No changes have occurred.
		- `PropertyChanged`&mdash;The change is associated with a property change in the data item.
		- `Sort`&mdash;The change is associated with a sorting operation.
		- `Group`&mdash;The change is associated with a grouping operation.
		- `Filter`&mdash;The change is associated with a filtering operation.
		- `Aggregate`&mdash;The change is associated with adding or removing an AggregateDescriptor from the Descriptors collection.
		- `Source`&mdash;The change is associated with changing the source.


## Modifying the Selection

The DataGrid delivers the `SelectionChanged` event which is triggered whenever the `SelectedItems` collection is changed. The `SelectionChanged` event handler receives the following parameters:
* The `sender` argument, which is of type `object`, but can be cast to the `RadDataGrid` type.
* A `DataGridSelectionChangedEventArgs` object, which provides the following properties:
	- `RemovedItems`&mdash;Gets a list of the removed items from the `SelectedItems` collection.
	- `AddedItems`&mdash;Gets a list of the added items to the `SelectedItems` collection.

For more information, see the article about the [`SelectionChanged` event of the .NET MAUI DataGrid]({%slug datagrid-selection-overview%}).

## Getting the Items in the Viewport

The DataGrid provides a `VisibleItemsChanged` event, which is triggered when the items in the viewport are changed during operations such as scrolling, resizing, grouping, sorting, filtering, and similar operations. The `VisibleItemsChanged` event handler receives the following parameters:

* The `sender` argument, which is of type `object`, but can be cast to the `RadDataGrid` type.
* A `DataGridVisibleItemsChangedEventArgs` object, which provides the following properties:
	- `AddedItems`&mdash;Gets the items that have become visible in the viewport since the last change.
	- `RemovedItems`&mdash;Gets the items that are no longer visible in the viewport since the last change.

## Changing the Current Cell

The DataGrid also supports the `CurrentCellChanged` event which is invoked when the current cell changes. The `CurrentCellChanged` event handler receives the following parameters:

* The `sender` argument, which is of type `object`, but can be cast to the `RadDataGrid` type.
* A `CurrentCellChangedEventArgs` object, which provides the following properties:
	- `OldCurrentCell`&mdash;Gets the previously `CurrentCell`.
	- `NewCurrentCell`&mdash;Gets the new `CurrentCell`.

For more information, see the article about the [`CurrentCellChanged` event in the .NET MAUI DataGrid]({%slug datagrid-current-cell%}).

## Reordering the Column

The DataGrid exposes the `ColumnReorderStarting`, `ColumnReordering`, `ColumnReorderCompleting`, and `ColumnReordered` events related to the column reordering operation. For more details, review the DataGrid [Columns Reordering]({%slug datagrid-columns-reordering%}#events) article. 

## Resizing the Column

The DataGrid resizing feature exposes a `ColumnUserResizeCompleted` event which is invoked when a column is resized by user interaction. The `ColumnUserResizeCompleted` event handler receives the following parameters:
* The `sender` argument, which is of type `object`, but can be cast to the `RadDataGrid` type.
* A `ColumnUserResizeCompletedEventArgs` object, which provides the following properties:
	- `Column` (`DataGridColumn`)&mdash;Gets the column that is resized.
	- `Width` (`double`)&mdash;Gets the width of the column that is resized.

## Additional Resources

- [.NET MAUI DataGrid Product Page](https://www.telerik.com/maui-ui/datagrid)
- [.NET MAUI DataGrid Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Setting the .NET MAUI DataGrid Columns]({%slug datagrid-columns-overview%})
- [Grouping in the DataGrid]({%slug datagrid-grouping-overview%})
- [Aggregating Data in the DataGrid]({%slug datagrid-aggregates%})
- [Using the DataGrid Commands]({%slug datagrid-commands-overview%})
- [Styling the Appearance of the DataGrid]({%slug datagrid-styling%})
