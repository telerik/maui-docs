---
title: Events
page_title: .NET MAUI TreeView Documentation - Events
description: Check our &quot;Events&quot; documentation article for Telerik TreeView for .NET MAUI control.
position: 7
slug: treeview-events
---

# Events

The .NET MAUI TreeView exposes the following events:

* `ItemTapped`&mdash;raises when an item is tapped. The `ItemTapped` event handler receives two parameters:
	* The `sender` argument which is of type object, but can be cast to the `RadTreeView` type.
	* A `ItemViewTappedEventArgs` object which has a reference to the tapped item through its `Item` property and to the tapped `View`.
	
* `ItemsSourceChanged`&mdash;raises when ItemsSource has changed. The `ItemHold` event handler receives two parameters:
	* The `sender` argument which is of type object, but can be cast to the **RadTreeView** type.
	* A `EventHandler` object.
	
* `SelectionChanged`&mdash;raises when the current selection changes. The `SelectionChanged` event handler receives two parameters:
	* The sender argument which is of type object, but can be cast to the `RadTreeView` type.
	* A `EventArgs` object which provides information on the collection changed event.


## See Also


