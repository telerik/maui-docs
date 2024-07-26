---
title: Overview
page_title: .NET MAUI CollectionView Documentation - Drag and Drop/Reorder
description: Review the Telerik UI for .NET MAUI CollectionView Drag and Drop feature.
position: 0
slug: collectionview-draganddrop-overview
tags: reorder, collectionview, drag-drop
---

# .NET MAUI CollectionView Drag and Drop

The .NET MAUI CollectionView provides drag and drop functionality which allows the end user to reorder its items. If the feature is enabled, when the user clicks and holds an item, the reorder mode is triggered and the user can move and release the item at the desired position. This also performs a reorder operation on the data. 

![.NET MAUI CollectionView Reorder Items](../images/collectionview-itemsreorder.gif)

To enable the reorder functionality, set the `IsItemsReorderEnabled` property to `True`.

Here is a quick example of a CollectionView with enabled reordering:

**1.** Define the following business object:

<snippet id='collectionview-datamodel' />

**2.** Create a `ViewModel` class as shown below:

<snippet id='collectionview-viewmodel' />

**3.** Add the `RadCollectionView` definition with `IsItemsReorderEnabled` set to `True`:

<snippet id='collectionview-reorder-items' />

## See Also

- [DragVisual and ReorderIndicator Templates]({%slug collectionview-draganddrop-templates%})
- [Reorder Grouped Items]({%slug collectionview-reorder-grouped-items%})
- [Drag and Drop between CollectionViews]({%slug collectionview-drag-and-drop-between-collectionviews%})