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

   ![.NET MAUI TreeView Independent Mode](images/treeview-independent-mode.gif)

* `Recursive`&mdash;Specifies that the checkboxes are checked and unchecked recursively. The checked state of the parent item is propagated to its children.

   ![.NET MAUI TreeView Recursive Mode](images/treeview-recursive-mode.gif)

> To display checkboxes in the TreeView item, set the `CheckBoxMode` to `Independent` or `Recursive`.

## Checked Items Collection

The control exposes a `CheckedItems` collection (`IList`). The collection holds the items that are currently checked.

## Programmatically Check or Uncheck All Items

The TreeView exposes two methods that enable you to programmatically check or uncheck all items:

* `CheckAll()`&mdash;Checks all items in the control.
* `UnCheckAll()`&mdash;Unchecks all items in the control.

## See Also

* [Commands]({%slug treeview-commands%})
* [Expand/Collapse]({%slug treeview-expand-collapse%})
