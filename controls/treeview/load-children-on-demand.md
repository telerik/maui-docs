---
title: Load Children on Demand
page_title: .NET MAUI TreeView Documentation - Load Children on Demand
description: Learn how to load subitems on demand in the TreeView control for .NET MAUI.
position: 7
slug: treeview-load-children-on-demand
---

# .NET MAUI TreeView Load Children on Demand

The performance of the Telerik UI for .NET MAUI TreeView control when operating with huge amount of items is significantly optimized through its load children on demand feature. 
This mechanism lets the nodes load their child nodes as the user expands the parent by clicking on the expand icon for desktop and tapping on the item on mobile.

![.NET MAUI TreeView Load Children on Demand](images/treeview-expand-collapse.gif)

Enable the TreeView Load Children on Demand feature:

**1.** Set the `IsLoadChildrenOnDemandEnabled` (`bool`) property. The property specifies a value indicating whether load on demand is enabled.

**2,** Use the `LoadChildrenOnDemand` event or `LoadChildrenOnDemandCommand` command to load the items.

## Event

The TreeView exposes the following event for loading children on demand. 

* `LoadChildrenOnDemand`&mdash;Raised when loading an item on demand. The `LoadChildrenOnDemand` event handler receives two parameters:
	* The `sender` argument, which is of type `object`, but can be cast to the `RadTreeView` type.
	* A `TreeViewLoadChildrenOnDemandEventArgs` object, which has a reference to:
		* the item through its `Item`(`object`) property.

## Command

The TreeView exposes the following command for loading children on demand. 

* `LoadChildrenOnDemandCommand`&mdash;Specfies a command to execute when loading an item on demand. The command acceps a parameter of type `Telerik.Maui.Controls.TreeView.TreeViewLoadChildrenOnDemandCommandContext`. 

## Example: TreeView Load Children on Demand Command

**1.** Define the TreeView control:

<snippet id='treeview-load-children-on-demand-command' />

**2.** Add a sample data model:

<snippet id='treeview-load-command-datamodel' />

**3.** Define the ViewModel with the `LoadChildrenOnDemand` implementation:

<snippet id='load-children-on-demand-command-viewmodel' />

> For runnable examples demonstrating the TreeView Load Children on Demand event and command, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **TreeView > Load Children on Demand**.

## See Also

* [CheckBoxes in TreeView]({%slug treeview-checkboxes%})
* [Styling the TreeView Item]({%slug treeview-item-style%})
* [Scrolling options]({%slug treeview-scrolling%})
* [Multiple and Single Selection]({%slug treeview-selection%})
* [Events]({%slug treeview-events%})
* [Available Commands in .NET MAUI TreeView]({%slug treeview-commands%})