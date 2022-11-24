---
title: Events
page_title: .NET MAUI ListView Documentation - Events
description: Explore the Telerik UI for .NET MAUI ListView Events like Item Events, Selection Events, Group/Reorder Events and Swipe Events.
position: 12
slug: listview-features-events
previous_url: /controls/listview/listview-features-events
tags: events
---

# .NET MAUI ListView Events

The ListView component exposes a set of events.

## Item Events

* `ItemTapped`&mdash;Occurs when an item is tapped. The `ItemTapped` event handler receives two parameters:
	* The sender argument which is of type object, but can be cast to the `RadListView` type.
	* An `ItemTapEventArgs` object which has a reference to the tapped item through its `Item` property.

* `ItemHold`&mdash;Occurs when the end user is holding on a specific item. The `ItemHold` event handler receives two parameters:
	* The sender argument which is of type object, but can be cast to the `RadListView` type.
	* An `ItemHoldEventArgs` object which has a reference to the held item through its `Item` property.

* `RefreshRequested`&mdash;Occurs when the pull-to-refresh gesture is triggered. The `RefreshRequested` event handler receives two parameters:
	* The sender argument which is of type object, but can be cast to the `RadListView` type.
	* A `PullToRefreshRequestedEventArgs` object which provides Cancel property used to cancel the pull-to-refresh operation.

	>tip For more details on the `RefreshRequested` event usage, refer to the [Pull to Refresh]({%slug listview-features-pull-to-refresh%}) topic.

## Selection Events

The `SelectionChanged` occurs when the `SelectionItems` collection is updated. The `SelectionChanged` event handler receives two parameters:

* The sender argument which is of type object, but can be cast to the `RadListView` type.
* A `NotifyCollectionChangedEventArgs` object which provides information on the collection changed event. For more details, refer to the [NotifyCollectionChangedEventArgs Class](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.notifycollectionchangedeventargs) topic.

## Group/Reorder Events

* `GroupHeaderTapped`&mdash;Occurs when a group header of a grouped ListView is tapped. The `GroupHeaderTapped` event handler receives two parameters:
	* The sender argument which is of type object, but can be cast to the `RadListView` type.
	* A `GroupHeaderTapEventArgs` object which provides the following properties:
		- `Key`&mdash;Gets the specific key for the group.
		- `Items`&mdash;Gets the child items of the group.

* `ReorderStarting`&mdash;Occurs when a reorder operation is about to start. The `ReorderStarting` event handler receives two parameters:
	* The sender argument which is of type object, but can be cast to the `RadListView` type.
	* A `ReorderStartingEventArgs` object provides the following properties:
		- `Item`&mdash;Gets the item that is about to be dragged.
		- `Cancel`&mdash;A boolean property which can be used to cancel the reorder operation.

* `ReorderEnded`&mdash;Occurs when a reorder operation has ended. The `ReorderEnded` event handler receives two parameters:
	* The sender argument which is of type object, but can be cast to the `RadListView` type.
	* A `ReorderEndedEventArgs` object which has a reference to the item that was reordered through its `Item` property.

## Swipe Events

The ListView exposes a few useful events related to the item swiping feature, namely `ItemSwipeStarting`, `ItemSwiping` and `ItemSwipeCompleted`. For detailed information on using the swiping events, refer to the [Cell Swipe]({%slug listview-features-cell-swipe %}) topic.

## See Also

 - [Selection]({%slug listview-features-selection%})
 - [Grouping]({%slug listview-features-grouping%})
 - [Reordering]({%slug listview-features-reorder-items%})
 - [Pull to Refresh]({%slug listview-features-pull-to-refresh%})
 - [Cell Swipe]({%slug listview-features-cell-swipe %})
