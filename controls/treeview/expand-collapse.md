---
title: Expand-Collapse Items
page_title: .NET MAUI TreeView Documentation - Expand and Collapse Items
description: "Review how to expand/collapse items when in the Treeview for .NET MAUI control."
position: 2
slug: treeview-expand-collapse
---

# Expanding and collapsing TreeView items

RadTreeView exposes useful methods which can be utilized in order to control the states of its items. You can use the following methods to chnage the state of all items:

* `ExpandAll()`&mdash;xpands all items from the source collection
* `CollapseAll()`&mdash;Collapses all items from the source collection

## Example

TreeView deifnition:

<snippet id='treeview-expand-collapse' />

`ExpandAll` method called on a button click:

<snippet id='treeview-expand-all-method' />

`CollapseAll` method called on a button click:

<snippet id='treeview-collapse-all-method' />

Data model:

<snippet id='treeview-getting-started-item' />

ViewModel:

<snippet id='treeview-getting-started-viewmodel' />

>important For the Treeview Expand and Collapse example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) TreeView -> Expand and Collapse category.

## See Also

* [CheckBoxes]({%slug treeview-checkboxes%})
* [Styling]({%slug treeview-item-style%})
* [CheckBoxes]({%slug treeview-checkboxes%})
* [Styling]({%slug treeview-item-style%})
* [Scrolling]({%slug treeview-scrolling%})
* [Selection]({%slug treeview-selection%})
* [Events]({%slug treeview-events%})
* [Commands]({%slug treeview-commands%})