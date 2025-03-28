---
title: CheckBox Elements
page_title: .NET MAUI TreeView Documentation - CheckBox Elements
description: Discover the CheckBox elements in the TreeView for .NET MAUI control and learn how to use and configure them.
position: 3
slug: treeview-checkboxes
---

# Checkbox Elements

The TreeView for .NET MAUI allows you to show checkbox elements and check specific items from its `ItemsSource`. The checked items are added to the `CheckedItems` property of the control. You can also control the visibility of the checkbox elements as well as their state propagation.

## Checkbox State Propagation

You can control the state propagation by setting the `CheckBoxMode` property (enum of type `Telerik.Maui.Controls.TreeView.TreeViewCheckBoxMode`). The `TreeViewCheckBoxMode` enum consists of the following values:

* `None`(default)&mdash;Specifies that no checkboxes are displayed in the control.
* `Independent`&mdash;Specifies that the checkboxes are checked and unchecked independently. The checked state of the parent item is not propagated to its children.
* `Recursive`&mdash;Specifies that the checkboxes are checked and unchecked recursively. The checked state of the parent item is propagated to its children.

## Recursive CheckBox Mode and Load Children on Demand

Consider the following scenarios when using the TreeView `Recursive` `CheckBoxMode` in a combination with the `LoadChildrenOnDemand` feature:

1. When checking the checkbox element of the parent item without loading the children, this parent item is added to the `CheckedItems` collection (the children are not).
2. When loading the children of the parent node by pressing the expand icon, and the checkbox of the parent node is checked, all child data items must be manually added to the `CheckedItems` collection.

Here is how the Independent `CheckBoxMode` looks:

![.NET MAUI TreeView Independent Mode](images/treeview-independent-mode.gif)

Here is how the Recursive `CheckBoxMode` looks:

![.NET MAUI TreeView Recursive Mode](images/treeview-recursive-mode.gif)

> To display checkboxes in the TreeView item, set the `CheckBoxMode` to `Independent` or `Recursive`.

## Checked Items Collection

The control exposes a `CheckedItems` collection (`IList`). The collection holds the items that are currently checked.

## Programmatically Check or Uncheck Items

The TreeView exposes methods and commands that enable you to programmatically check or uncheck item/all items.

The available methods are:

* `Check(params object[] itemPath)`&mdash;Checks the item in hierarchy with the specified path. The `itemPath` parameter specifies the path to an item in the hierarchy to expand. The path is a collection if unique identifiers of items. The first element of the path identifies an item at the root level. The second element of the path identifies a child of the root item etc. The `Telerik.Maui.Controls.TreeView.TreeViewDescriptor.IdentityMemberPath` property has to be used to specify the unique identifier at each level of the hierarchy.
* `UnCheck(params object[] itemPath)`&mdash;Unchecks the item in hierarchy with the specified path. The `itemPath` parameter specifies the path to an item in the hierarchy to expand. The path is a collection if unique identifiers of items. The first element of the path identifies an item at the root level. The second element of the path identifies a child of the root item etc. The `Telerik.Maui.Controls.TreeView.TreeViewDescriptor.IdentityMemberPath` property has to be used to specify the unique identifier at each level of the hierarchy.
* `CheckAll()`&mdash;Checks all items in the control.
* `UnCheckAll()`&mdash;Unchecks all items in the control.

The available commands are:

* `CheckCommand`&mdash;Gets a command to check a specific item in the control. The command accepts a parameter specifying the path to the item. The path is a collection if unique identifiers of items. The first element of the path identifies an item at the root level. The second element of the path identifies a child of the root item etc. The `Telerik.Maui.Controls.TreeView.TreeViewDescriptor.IdentityMemberPath` property has to be used to specify the unique identifier at each level of the hierarchy.
* `UncheckCommand`&mdash;Gets a command to uncheck a specific item in the control. The command accepts a parameter specifying the path to the item. The path is a collection if unique identifiers of items. The first element of the path identifies an item at the root level. The second element of the path identifies a child of the root item etc. The `Telerik.Maui.Controls.TreeView.TreeViewDescriptor.IdentityMemberPath` property has to be used to specify the unique identifier at each level of the hierarchy.
* `CheckAllCommand`&mdash;Gets a command to expand all items in the control.
* `UncheckAllCommand`&mdash;Gets a command to collapse all items in the control.

Here is how the TreeView CheckAll/UncheckAll command execution looks:

![.NET MAUI TreeView Check and Uncheck](images/treeview-check-uncheck-items.gif)

Here is how the TreeView Check/Uncheck command execution looks:

![.NET MAUI TreeView Check and Uncheck](images/treeview-check-uncheck-item.gif)

> For a runnable example demonstrating the TreeView Check and Uncheck feature, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **TreeView > Commands category**.

## See Also

* [Expand and Collapse TreeView Items]({%slug treeview-expand-collapse%})
* [Styling the TreeView Item]({%slug treeview-item-style%})
* [Scrolling options]({%slug treeview-scrolling%})
* [Multiple and Single Selection]({%slug treeview-selection%})
* [Events]({%slug treeview-events%})
* [Available Commands in .NET MAUI TreeView]({%slug treeview-commands%})
