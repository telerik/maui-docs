---
title: Expand-Collapse Items
page_title: .NET MAUI TreeView Documentation - Expand and Collapse Items
description: Review how to expand and collapse items when working with the TreeView control for .NET MAUI.
position: 2
slug: treeview-expand-collapse
---

# Expanding and Collapsing TreeView Items

The `RadTreeView` control exposes methods and commands that allow you to control the expand/collapse state of its item/all items.

The available methods are:

* `Expand(params object[] itemPath)`&mdash;Expands the item in hierarchy with the specified path. The `itemPath` parameter specifies the path to an item in the hierarchy to expand. The path is a collection if unique identifiers of items. The first element of the path identifies an item at the root level. The second element of the path identifies a child of the root item etc. The `Telerik.Maui.Controls.TreeView.TreeViewDescriptor.IdentityMemberPath` property has to be used to specify the unique identifier at each level of the hierarchy.
* `Collapse(params object[] itemPath)`&mdash;Collapses the item in hierarchy with the specified path. The `itemPath` parameter specifies the path to an item in the hierarchy to collapse. The path is a collection if unique identifiers of items. The first element of the path identifies an item at the root level. The second element of the path identifies a child of the root item etc. The `Telerik.Maui.Controls.TreeView.TreeViewDescriptor.IdentityMemberPath` property has to be used to specify the unique identifier at each level of the hierarchy.
* `ExpandAll()`&mdash;Expands all items in the source collection.
* `CollapseAll()`&mdash;Collapses all items in the source collection.

The available commands are:

* `ExpandCommand`&mdash;Gets a command to expand a specific item in the control. The command accepts a parameter specifying the path to the item. The path is a collection if unique identifiers of items. The first element of the path identifies an item at the root level. The second element of the path identifies a child of the root item etc. The `Telerik.Maui.Controls.TreeView.TreeViewDescriptor.IdentityMemberPath` property has to be used to specify the unique identifier at each level of the hierarchy.
* `CollapseCommand`&mdash;Gets a command to collapse a specific item in the control. The command accepts a parameter specifying the path to the item. The path is a collection if unique identifiers of items. The first element of the path identifies an item at the root level. The second element of the path identifies a child of the root item etc. The `Telerik.Maui.Controls.TreeView.TreeViewDescriptor.IdentityMemberPath` property has to be used to specify the unique identifier at each level of the hierarchy.
* `ExpandAllCommand`&mdash;Gets a command to expand all items in the control.
* `CollapseAllCommand`&mdash;Gets a command to collapse all items in the control.

> On Android and iOS, when tapping on the TreeView item, the item gets expanded. On WinUI and MacCatalyst, the item gets expanded when tapping on the arrow **>**. 

![.NET MAUI TreeView Expand and Collapse](images/treeview-expand-collapse.gif)

## Example: Expanding an Item Using the Expand Method

Review the following kb article: [Using the Expand Method of TreeView in UI for .NET MAUI]({%slug expand-item-method-treeview-dotnet-maui%}). The example demonstrates how to use the `Expand` method of the TreeView control in UI for .NET MAUI to expand specific nodes programmatically.

## Example: Expanding and Collapsing Item Using the Commands

Review the following kb article: [Using Expand and Collapse Commands in TreeView for .NET MAUI]({%slug expand-collapse-item-treeview-dotnet-maui%}). The example demonstrates how to expand and collapse specific items in the TreeView control for .NET MAUI using commands. The commands take a path as a parameter, entered in an Entry control, and convert it into an item path using a converter.

## Example: Expanding and Collapsing All TreeView Items

**1.** Define the TreeView control:

<snippet id='treeview-expand-collapse' />

**2.** Add the `ExpandAll` method called on a button click:

<snippet id='treeview-expand-all-method' />

**3.** Add the `CollapseAll` method called on a button click:

<snippet id='treeview-collapse-all-method' />

**4.** Add the data model:

<snippet id='treeview-getting-started-item' />

**5.** Add the ViewModel:

<snippet id='treeview-getting-started-viewmodel' />

Here is how the TreeView Expand/Collapse All command execution looks:

![.NET MAUI TreeView Expand and Collapse](images/treeview-expand-collapse.gif)

> For a runnable example demonstrating the TreeView Expand and Collapse feature, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **TreeView > Expand and Collapse or TreeView > Commands**.

## See Also

* [CheckBoxes in TreeView]({%slug treeview-checkboxes%})
* [Styling the TreeView Item]({%slug treeview-item-style%})
* [Scrolling options]({%slug treeview-scrolling%})
* [Multiple and Single Selection]({%slug treeview-selection%})
* [Events]({%slug treeview-events%})
* [Available Commands in .NET MAUI TreeView]({%slug treeview-commands%})