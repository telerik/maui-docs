---
title: Overview
page_title: .NET MAUI CollectionView Documentation - Drag and Drop/Reorder
description: Review the Telerik UI for .NET MAUI CollectionView Drag and Drop feature.
position: 0
slug: collectionview-dragdrop-overview
tags: reorder, collectionview, drag-drop
---

# .NET MAUI CollectionView Drag and Drop

The .NET MAUI CollectionView provides drag and drop functionality which allows the end user to reorder its items.

![.NET MAUI CollectionView Reorder Items](../images/collectionview-itemsreorder.gif)

To enable the reorder functionality, set the `IsDragDropEnabled` property to `True`. To start reordering the items, the end user has to click and hold an item on mobile (Android and iOS) and on dekstop (WinUi and MacCatalyst) after clicking on the item, the item can be dragged. In this way, the drag is triggered and the user can move and release (drop) the item at the desired position. This also performs a reorder operation on the data. 

Here is a quick example of a CollectionView with enabled drag-and-drop:

**1.** Define the following business object:

<snippet id='collectionview-datamodel' />

**2.** Create a `ViewModel` class as shown below:

<snippet id='collectionview-viewmodel' />

**3.** Add the `RadCollectionView` definition with `IsDragDropEnabled` set to `True`:

<snippet id='collectionview-reorder-items' />

## See Also

- [DragVisual and DropIndicator Templates]({%slug collectionview-dragdrop-templates%})
- [Drag abd Drop Grouped Items]({%slug collectionview-dragdrop-grouped-items%})
- [Drag and Drop between CollectionViews]({%slug collectionview-dragdrop-between-collectionviews%})
