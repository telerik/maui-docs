---
title: CheckBox Elements
page_title: .NET MAUI TreeView Documentation - CheckBox Elements
description: "Review the checkbox elements in the Treeview for .NET MAUI."
position: 3
slug: treeview-checkboxes
---

# CheckBox elements

Telerik TreeView for .NET MAUI supports showing CheckBox elements and checking specific items from its ItemsSource. The checked items are added to the CheckedItems property of the control. You can also control the Visibility of the CheckBox elements as well as their state propagation.

## CheckBox State Propagation

You can control the state propagation by setting the `CheckBoxMode` property(enum of type `Telerik.Maui.Controls.TreeView.TreeViewCheckBoxMode`). The `TreeViewCheckBoxMode` enum consists of the following values:

* (Default value)`None`&mdash;Specifies that no check boxes are displayed in the control.
* `Independent`&mdash;Specifies that the check boxes are checked and unchecked independently. The checked state of the parent item is not propagated to its children..
* `Recursive`&mdash;Specifies that the check boxes are checked and unchecked recursively. The checked state of the parent item is propagated to its children.

>importnat In order to display checkboxes in the TreeView item you have to set the `CheckBoxMode` to `Independent` or `Recursive`.

## CheckedItems collection

The control exposes a collection&mdash;`CheckedItems` collection(`IList`). The collection holds the items that are currently checked.

## Programmatically check uncheck all items

The TreeView exposes two methods to programmatically check or uncheck all items:

* `CheckAll()`&mdash;Checks all items in the control.
* `UnCheckAll()`&mdash;Unchecks all items in the control.

## See Also

* [Commands]({%slug treeview-commands%})
* [Expand/Collapse]({%slug treeview-expand-collapse%})
