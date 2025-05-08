---
title: Load Children on Demand
page_title: .NET MAUI TreeView Documentation - Load Children on Demand
description: Learn how to load subitems on demand in the TreeView control for .NET MAUI.
position: 7
slug: treeview-load-children-on-demand
---

# .NET MAUI TreeView Load Children on Demand

The Load Children on Demand feature optimizes the performance of the Telerik UI for .NET MAUI TreeView control when operating with a huge amount of items. This mechanism lets the nodes load their child nodes as the user expands the parent by clicking on the expand icon for desktop and tapping on the item on mobile.

![.NET MAUI TreeView Load Children on Demand](images/treeview-loadondemand.gif)

To enable the TreeView Load Children on Demand feature:

**1.** Set the `IsLoadChildrenOnDemandEnabled` (`bool`) property. The property specifies a value indicating whether load on demand is enabled.

**2.** Use the `LoadChildrenOnDemand` event or `LoadChildrenOnDemandCommand` command to load the items.

## Load Children on Demand and Recursive CheckBox Mode

Consider the following scenarios when using the TreeView `LoadChildrenOnDemand` feature in a combination with the `Recursive` `CheckBoxMode`:

* When checking the checkbox element of the parent item without loading the children, this parent item is added to the `CheckedItems` collection (the children are not).
* When loading the children of the parent node by pressing the expand icon, and the checkbox of the parent node is checked, all child data items must be manually added to the `CheckedItems` collection.

> For a runnable example demonstrating the TreeView `Recursive` `CheckBoxMode` and Load Children on Demand scenario, see the [Handling TreeView Load Children on Demand with Recursive CheckBox Mode]({%slug treeview-net-maui-load-children-checkbox-recursive%}) article.

## Event

The TreeView exposes the following event for loading children on demand. 

* `LoadChildrenOnDemand`&mdash;Raised when loading an item on demand. The `LoadChildrenOnDemand` event handler receives two parameters:
	* The `sender` argument, which is of type `object`, but can be cast to the `RadTreeView` type.
	* A `TreeViewLoadChildrenOnDemandEventArgs` object, which has a reference to:
		* the item through its `Item`(`object`) property.

## Command

The TreeView exposes the following command for loading children on demand. 

* `LoadChildrenOnDemandCommand`&mdash;Specifies a command to execute when loading an item on demand. The command accepts a parameter of type `Telerik.Maui.Controls.TreeView.TreeViewLoadChildrenOnDemandCommandContext`. 

The next example shows how to use the Load Children on Demand command in the TreeView.

**1.** Define the TreeView control:

<snippet id='treeview-load-children-on-demand-command' />

**2.** Add a sample data model:

<snippet id='treeview-load-command-datamodel' />

**3.** Define the ViewModel with the `LoadChildrenOnDemandCommand` implementation:

<snippet id='load-children-on-demand-command-viewmodel' />

> For runnable examples demonstrating the TreeView Load Children on Demand command, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **TreeView > Load Children on Demand**.

## See Also

* [CheckBoxes in TreeView]({%slug treeview-checkboxes%})
* [Styling the TreeView Item]({%slug treeview-item-style%})
* [Scrolling options]({%slug treeview-scrolling%})
* [Multiple and Single Selection]({%slug treeview-selection%})
* [Events]({%slug treeview-events%})
* [Available Commands in .NET MAUI TreeView]({%slug treeview-commands%})
