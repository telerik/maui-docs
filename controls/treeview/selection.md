---
title: Selection
page_title: .NET MAUI TreeView Documentation - Selection
description: "Review all selection options TreeView for .NET MAUI provides."
position: 6
slug: treeview-selection
---

# Selection

The TreeView for .NET MAUI exposes selection feature. It allows single or multiple selection of the ListView items. This feature provides both visual and programmatic feedback for the actions of the user. Also you can disable the selection.

## Selection Mode

The TreeView provides three selection modes, which allow you to manipulate the type of selection. This is controlled by the `SelectionMode` (`Microsoft.Maui.Controls.SelectionMode`) property which has the following entries:

- `None`&mdash;This mode doesn't allow users to select an item.
- `Single`&mdash;This is the default selection mode. It allows users to select only one item.
- `Multiple`&mdash;This mode allows users to select more than one item.

![.NET MAUI Treeview](images/treeview.png)

## Setting the selected item

The ListView provides the `SelectedItem` (`object`) property, which specifies the last selected item of the ListView.

## Selected Items Collection

The TreeView provides the `SelectedItems` (`IList`) property, which is a read-only collection used to get the currently selected items.

## Selection Events

The Treeview provides the `SelectionChanged` event, which is raised when the current selection changes. The `SelectionChanged` event handler receives two parameters:

* The sender argument which is of type object, but can be cast to the `RadTreeView` type.
* A `EventArgs` object which provides information on the collection changed event.


>important For the Treeview Selections example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) TreeView -> Selection category.

## See Also

