---
title: Events
page_title: .NET MAUI TreeView Documentation - Events
description: Check our &quot;Events&quot; documentation article for Telerik TreeView for .NET MAUI control.
position: 7
slug: treeview-events
---

# .NET MAUI TreeView Events

The .NET MAUI TreeView exposes the following events:

* `ItemTapped`&mdash;Raises when an item is tapped. The `ItemTapped` event handler receives two parameters:
	* The `sender` argument which is of type object, but can be cast to the `RadTreeView` type.
	* A `ItemViewTappedEventArgs` object which has a reference to the
		* tapped item through its `Item`(`object`) property 
		* tapped `View`(`ItemView`)
		* and the `Handled`(`bool`) property&mdash;Indicates whether the event handler has already handled the tap event. When set to true, the default handling of the tap event is not executed. When set to false, the default handling of the tap event is executed.

>important On Android and iOS when tapping on the TreeView item the item gets expanded. On WinUI and MacCatalyst the item gets expanded when tapping on the arrow `>`. 

* `ItemsSourceChanged`&mdash;Raises when ItemsSource has changed. The `ItemHold` event handler receives two parameters:
	* The `sender` argument which is of type object, but can be cast to the **RadTreeView** type.
	* A `EventHandler` object.
	
* `SelectionChanged`&mdash;Raises when the current selection changes. The `SelectionChanged` event handler receives two parameters:
	* The sender argument which is of type object, but can be cast to the `RadTreeView` type.
	* A `EventArgs` object which provides information on the collection changed event.


**Example with ItemTapped**

TreeView definition: 

<snippet id='treeview-itemtapped'/>

ItemTapped event: 

<snippet id='treeview-itemtapped-event'/>

Data model: 

<snippet id='treeview-events-data'/>

ViewModel: 

<snippet id='treeview-events-viewmodel'/>

**Example with SelectionChanged**

TreeView definition: 

<snippet id='treeview-selectionchanged'/>

ItemTapped event: 

<snippet id='treeview-selectionchanged-event'/>

Data model: 

<snippet id='treeview-events-data'/>

ViewModel: 

<snippet id='treeview-events-viewmodel'/>

>important For the Treeview Events example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) TreeView -> Events category.

## See Also

* [Expand/Collapse]({%slug treeview-expand-collapse%})
* [CheckBoxes]({%slug treeview-checkboxes%})
* [Styling]({%slug treeview-item-style%})
* [Scrolling]({%slug treeview-scrolling%})
