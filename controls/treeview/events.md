---
title: Events
page_title: .NET MAUI TreeView Documentation - Events
description: Review TreeView events that are raised when item is tapped, selected and source is changed. 
position: 8
slug: treeview-events
---

# .NET MAUI TreeView Events

The .NET MAUI TreeView emits a set of events that allow you to configure the component's behavior in response to specific user actions.

The .NET MAUI TreeView exposes the following events:

* `ItemTapped`&mdash;Raised when an item is tapped. The `ItemTapped` event handler receives two parameters:
	* The `sender` argument, which is of type `object`, but can be cast to the `RadTreeView` type.
	* A `ItemViewTappedEventArgs` object, which has a reference to:
		* the tapped item through its `Item`(`object`) property.
		* the tapped `View`(`ItemView`).
		* the `Handled`(`bool`) property&mdash;Indicates whether the event handler has already handled the tap event. When set to `true`, the default handling of the tap event is not executed. When set to `false`, the default handling of the tap event is executed.

	> On Android and iOS, when tapping the TreeView item, the item gets expanded. On WinUI and MacCatalyst, the item gets expanded when tapping on the arrow **>**. 

* `ItemHolding`&mdash;Raised when an item is held. The `ItemHolding` event handler receives two parameters:
	* The `sender` argument, which is of type `object`, but can be cast to the `RadTreeView` type.
	* A `ItemViewHoldingEventArgs` object which has a reference to:
		* the tapped item through its `Item`(`object`) property.
		* the tapped `View`(`ItemView`).
		* the `Handled`(`bool`) property&mdash;Indicates whether the event handler has already handled the hold event. When set to `true`, the default handling of the hold event is not executed. When set to `false`, the default handling of the hold event is executed.

* `ItemsSourceChanged`&mdash;Raised when `ItemsSource` has changed. The `ItemsSourceChanged` event handler receives two parameters:
	* The `sender` argument, which is of type `object`, but can be cast to the `RadTreeView` type.
	* An `EventHandler` object.
	
* `SelectionChanged`&mdash;Raised when the current selection changes. The `SelectionChanged` event handler receives two parameters:
	* The sender argument, which is of type `object`, but can be cast to the `RadTreeView` type.
	* A `EventArgs` object, which provides information on the `SelectionChanged` event.

* `LoadChildrenOnDemand`&mdash;Raised when loading an item on demand. The `LoadChildrenOnDemand` event handler receives two parameters:
	* The `sender` argument, which is of type `object`, but can be cast to the `RadTreeView` type.
	* A `TreeViewLoadChildrenOnDemandEventArgs` object, which has a reference to:
		* the item through its `Item`(`object`) property.
		

* `ItemChecked`&mdash;Raised when an item is checked after a user interaction. The `ItemChecked` event handler receives two parameters:
	* The `sender` argument, which is of type `object`, but can be cast to the `RadTreeView` type.
	* A `TreeViewItemViewInteractionEventArgs` object which has a reference to:
		* the tapped item through its `Item`(`object`) property.
		* the tapped `View`(`ItemView`).

* `ItemUnchecked`&mdash;Raised when an item is unchecked after a user interaction. The `ItemUnchecked` event handler receives two parameters:
	* The `sender` argument, which is of type `object`, but can be cast to the `RadTreeView` type.
	* A `TreeViewItemViewInteractionEventArgs` object which has a reference to:
		* the tapped item through its `Item`(`object`) property.
		* the tapped `View`(`ItemView`).

* `ItemExpanded`&mdash;Raised when an item is expanded after a user interaction. The `ItemExpanded` event handler receives two parameters:
	* The `sender` argument, which is of type `object`, but can be cast to the `RadTreeView` type.
	* A `TreeViewItemViewInteractionEventArgs` object which has a reference to:
		* the tapped item through its `Item`(`object`) property.
		* the tapped `View`(`ItemView`).

* `ItemCollapsed`&mdash;Raised when an item is collapsed after a user interaction. The `ItemCollapsed` event handler receives two parameters:
	* The `sender` argument, which is of type `object`, but can be cast to the `RadTreeView` type.
	* A `TreeViewItemViewInteractionEventArgs` object which has a reference to:
		* the tapped item through its `Item`(`object`) property.
		* the tapped `View`(`ItemView`).

## Using the ItemTapped Event

The following example demonstrates how to use the `ItemTapped` event:

**1.** Define the `RadTreeView` control: 

<snippet id='treeview-itemtapped'/>

**2.** Add the `ItemTapped` event: 

<snippet id='treeview-itemtapped-event'/>

**3.** Add the data model: 

<snippet id='treeview-events-data'/>

**4.** Add the ViewModel: 

<snippet id='treeview-events-viewmodel'/>

This is the result on Android:

![.NET MAUI TreeView ItemTapped Event](images/treeview-itemtapped.gif)

## Using the SelectionChanged Event

The following example demonstrates how to use the `SelectionChanged` event:

**1.** Define the `RadTreeview` control: 

<snippet id='treeview-selectionchanged'/>

**2.** Add the `ItemTapped` event: 

<snippet id='treeview-selectionchanged-event'/>

**3.** Add the data model: 

<snippet id='treeview-events-data'/>

**4.** Add the ViewModel: 

<snippet id='treeview-events-viewmodel'/>

This is the result on Android:

![.NET MAUI TreeView SelectionChanged Event](images/treeview-selection.gif)

> For a runnable example demonstrating the TreeView events, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **TreeView > Events**.

## See Also

* [Expand and Collapse TreeView Items]({%slug treeview-expand-collapse%})
* [CheckBoxes in TreeView]({%slug treeview-checkboxes%})
* [Styling the TreeView Item]({%slug treeview-item-style%})
* [Scrolling options]({%slug treeview-scrolling%})
* [Multiple and Single Selection]({%slug treeview-selection%})
* [Available Commands in .NET MAUI TreeView]({%slug treeview-commands%})
