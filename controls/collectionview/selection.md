---
title: Selection
page_title: .NET MAUI CollectionView Documentation - Selection
description: The CollectionView for .NET MAUI exposes a selection feature that allows the user to select single or multiple items in the CollectionView control.
position: 4
slug: collectionview-selection
---

# .NET MAUI CollectionView Selection

The CollectionView for .NET MAUI exposes the Selection feature, which allows the user to select single or multiple items in the CollectionView. This feature provides both visual and programmatic feedback for the user's actions. If needed, you can disable the Selection.

## Selection Mode

The CollectionView provides three selection modes, which allow you to manipulate the selection type. This is controlled by the `SelectionMode` (`Microsoft.Maui.Controls.SelectionMode`) property which has the following entries:

- `None`&mdash;The users cannot select an item.
- `Single` (default)&mdash;The users can select only one item.
- `Multiple`&mdash;The users can select more than one item.

Check below how you can set `SelectionMode` in XAML and code-behind:

```XAML
<telerik:RadCollectionView x:Name="collectionView"
					       SelectionMode="Multiple" />
```
```C#
var collectionView = new RadCollectionView();
collectionView.SelectionMode = Microsoft.Maui.Controls.SelectionMode.Multiple;
```

## Setting the Selected Item

The CollectionView provides the `SelectedItem` (`object`) property, which specifies the last selected item of the CollectionView.

> For a runnable example demonstrating the TreeView `SelectedItem`, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **CollectionView > Selection**.

## Selected Items Collection

The CollectionView provides the `SelectedItems` collection of type `IList`. The collection contains the items that are currently selected in the control.

> For a runnable example demonstrating the CollectionView `SelectedItems`, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **CollectionView > Selection**.

## Selection Events

The CollectionView provides the `SelectionChanged` event, which is raised when the current selection changes. The `SelectionChanged` event handler receives two parameters:

* The sender argument, which is of type `object`, but can be cast to the `RadCollectionVieww` type.
* A `EventArgs` object, which provides information on the `SelectionChanged` event.

> For a runnable example demonstrating the TreeView events, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **CollectionView > Events**.

## See Also


