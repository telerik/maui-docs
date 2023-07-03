---
title: Expand-Collapse Items
page_title: .NET MAUI TreeView Documentation - Expand and Collapse Items
description: Review how to expand and collapse items when working with the TreeView control for .NET MAUI.
position: 2
slug: treeview-expand-collapse
---

# Expanding and Collapsing TreeView Items

The `RadTreeView` control exposes methods that allow you to control the state of its items:

* `ExpandAll()`&mdash;Expands all items in the source collection.
* `CollapseAll()`&mdash;Collapses all items in the source collection.

> On Android and iOS, when tapping on the TreeView item, the item gets expanded. On WinUI and MacCatalyst, the item gets expanded when tapping on the arrow **>**. 


![.NET MAUI TreeView Expand and Collapse](images/treeview-expand-collapse.gif)

## Example: Expanding and Collapsing TreeView Items

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

> For a runnable example demonstrating the TreeView Expand and Collapse feature, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **TreeView > Expand and Collapse**.

## See Also

* [CheckBoxes in TreeView]({%slug treeview-checkboxes%})
* [Styling the TreeView Item]({%slug treeview-item-style%})
* [Scrolling options]({%slug treeview-scrolling%})
* [Multiple and Single Selection]({%slug treeview-selection%})
* [Events]({%slug treeview-events%})
* [Available Commands in .NET MAUI TreeView]({%slug treeview-commands%})