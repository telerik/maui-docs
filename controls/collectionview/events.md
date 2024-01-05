---
title: Events
page_title: .NET MAUI CollectionView Documentation - Events
description: Explore the Telerik UI for .NET MAUI CollectionView Events like Item Events and Selection Events.
position: 13
slug: collectionview-events
tags: events
---

# .NET MAUI CollectionView Events

The Telerik UI for .NET MAUI CollectionView component exposes a set of events that users trigger through interaction. You can handle these events and customize the configuration of the UI component.

## Item Events

* `ItemTapped`&mdash;Raised when an item is tapped. The `ItemTapped` event handler receives two parameters:
	* The `sender` argument, which is of type `object`, but can be cast to the `CollectionView` type.
	* A `ItemViewTappedEventArgs` object, which has a reference to:
		* the tapped item through its `Item`(`object`) property.
		* the tapped `View`(`ItemView`).
		* the `Handled`(`bool`) property&mdash;Indicates whether the event handler has already handled the tap event. When set to `true`, the default handling of the tap event is not executed. When set to `false`, the default handling of the tap event is executed.

	> On Android and iOS, when tapping the TreeView item, the item gets expanded. On WinUI and MacCatalyst, the item gets expanded when tapping on the arrow **>**. 

* `ItemHolding`&mdash;Raised when an item is held. The `ItemHolding` event handler receives two parameters:
	* The `sender` argument, which is of type `object`, but can be cast to the `CollectionView` type.
	* A `ItemViewHoldingEventArgs` object which has a reference to:
		* the tapped item through its `Item`(`object`) property.
		* the tapped `View`(`ItemView`).
		* the `Handled`(`bool`) property&mdash;Indicates whether the event handler has already handled the hold event. When set to `true`, the default handling of the hold event is not executed. When set to `false`, the default handling of the hold event is executed.

* `ItemsSourceChanged`&mdash;Raised when `ItemsSource` has changed. The `ItemsSourceChanged` event handler receives two parameters:
	* The `sender` argument, which is of type `object`, but can be cast to the `CollectionView` type.
	* An `EventHandler` object.

## Selection Events

* `SelectionChanged`&mdash;Raised when the current selection changes. The `SelectionChanged` event handler receives two parameters:
	* The sender argument, which is of type `object`, but can be cast to the `RadTreeView` type.
	* A `EventArgs` object, which provides information on the `SelectionChanged` event.

## See Also

