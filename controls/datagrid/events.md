---
title: Events
page_title: .NET MAUI DataGrid Documentation - Events
description: Check our &quot;Events&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 9
slug: datagrid-events
description: Describing the events of the RadDataGrid
tags: events
---

# Events

The DataGrid component exposes a set of events.

* `LoadOnDemand`&mdash; Occurs when the load on demand is requested. The `LoadOnDemand` event handler receives two parameters:
	* The sender argument, which is of type object, but can be cast to the `RadDataGrid` type.
	* A `LoadOnDemandEventArgs` object, which provides the following property:
		- `IsDataLoaded`(`bool`)&mdash; Indicating whether the data is loaded.

For more information about LoadOnDemand event review the [DataGrid LoadOnDemand article]({%slug datagrid-features-loadondemand%}).


* `DistinctValuesLoading`&mdash;Occurs when loading the distinct values that will be displayed in the `Telerik.Maui.Controls.Compatibility.DataGrid.DataGridDistinctValuesFilterView`. The `DistinctValuesLoading` event handler receives two parameters:
	* The sender argument, which is of type object, but can be cast to the `RadDataGrid` type.
	* A `DistinctValuesLoadingEventArgs` object, which provides the following properties:
		- `DistinctValues`&mdash; Is a property which specifies a list of values of type `IEnumerable` which are to be displayed in the `DataGridDistinctValuesFilterView`.
		- `Column`&mdash; Is a readonly property of type `DataGridColumn` which gets the column for which the distinct values are being loaded.

For more information about Filtering options in DataGrid review the [DataGrid Filtering article]({%slug datagrid-filtering-overview%}).


* `DataBindingComplete`&mdash;Occurs when the associated DataGrid data(`ItemsSource`) has been successfully bound to the control or any data operation like Group, Sort or filter is applied.
	* The sender argument, which is of type object, but can be cast to the `RadDataGrid` type.
	* A `DataBindingCompleteEventArgs` object, which provides the following property:
		- `DataView`(`IDataViewCollection`)&mdash;Implementation that allows for traversing and/or manipulating the already computed data view.


* `SelectionChanged` event that is triggered whenever the `SelectedItems` collection is changed. The `SelectionChanged` event handler receives two parameters:
	* The sender argument, which is of type object, but can be cast to the `RadDataGrid` type.
	* A `DataGridSelectionChangedEventArgs` object, which provides the following properties:
		- `RemovedItems`&mdash;Gets a list of the removed items from the `SelectedItems` collection.
		- `AddedItems`&mdash;Gets a list of the added items to the `SelectedItems` collection.

For more information about `SelectionChanged` event review the [DataGrid Selection article]({%slug datagrid-selection-overview%}).


`CurrentCellChanged` event which is invoked when the current cell changes. The `CurrentCellChanged` event handler receives two parameters:
	* The sender argument, which is of type object, but can be cast to the `RadDataGrid` type.
	* A `CurrentCellChangedEventArgs` object, which provides the following properties:
		- `OldCurrentCell`&mdash;Gets the previously `CurrentCell`.
		- `NewCurrentCell`&mdash;Gets the new `CurrentCell`.

For more information about `CurrentCellChanged` event review the [DataGrid Current Cell article]({%slug datagrid-current-cell%}).


## Example

The following example demonstrates the usage of the `LoadOnDemand` event.

Define the LoadOnDemand method in XAML:

<snippet id ='datagrid-loadondemand-event-xaml'/>

Create the method defining the functionality of the event:

<snippet id='datagrid-loadondemand-event-csharp'/>

## See Also

 - [Filtering]({%slug datagrid-filtering-overview%})
 - [Grouping]({%slug datagrid-grouping-overview%})
 - [Selection]({%slug datagrid-selection-overview%})
 - [Load On Demand]({%slug datagrid-features-loadondemand%})
 - [Sorting]({%slug datagrid-sorting-overview%})
 - [Row Height]({%slug datagrid-row-height%})
 - [Editing]({%slug datagrid-editing%})
