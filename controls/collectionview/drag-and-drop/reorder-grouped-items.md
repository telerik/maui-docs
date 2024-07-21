---
title: Reorder Grouped Items
page_title: .NET MAUI CollectionView Documentation - Reorder Grouped Items
description: Review the Telerik UI for .NET MAUI CollectionView Reorder Grouped Items.
position: 1
slug: collectionview-reorder-grouped-items
tags: reorder, collectionview, drag-drop, grouping
---

# .NET MAUI CollectionView Reorder Grouped Items

The .NET MAUI CollectionView provides the option to customize its drag and drop behavior and implement custom logic when items are dropped. This can be useful when you need to allow the users to move items between different groups in a grouped scenario. 

To customize the behavior, you can create a new class that derives from `CollectionViewDragDropBehavior` and override its virtual methods, such as:

 - `CanStartDrag`(`CollectionViewDragDropState` state)&mdash;Returns a bool value specifying whether the drag operation can be started.
 - `CanDrop`(`CollectionViewDragDropState` state)&mdash;Returns a value specifying whether the current drop operation can be completed.
 - `Drop`(`CollectionViewDragDropState` state)&mdash; Completes the drop operation. This method is called only in the context of the drop target control.

 The following example demonstrates how you can implement a custom logic on Drop event to allow moving items between groups:

**1.** Add a sample `CollectionViewDragDropBehavior` class and override its `Drop` method:

<snippet id='collectionview-customdragdropbehavior' />

**2.** Add a CollectionView control to the page:

<snippet id='collectionview-reorder-grouping' />

**3.** Define the following business object:

<snippet id='collectionview-datamodel' />

**4.** Create a `ViewModel` class as shown below:

<snippet id='collectionview-viewmodel' />

## See Also

- [Drag and Drop Overview]({%slug collectionview-draganddrop-overview%})
- [DragVisual and ReorderIndicator Templates]({%slug collectionview-draganddrop-templates%})
- [Drag and Drop between CollectionViews]({%slug collectionview-drag-and-drop-between-collectionviews%})
