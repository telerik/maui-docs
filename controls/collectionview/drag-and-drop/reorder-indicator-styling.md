---
title: Reorder Indicator Styling
page_title: .NET MAUI CollectionView Documentation - Reorder Indicator Styling
description: Review the Telerik UI for .NET MAUI CollectionView Reorder Indicator Styling.
position: 4
slug: collectionview-reorder-indicator-styling
tags: reorder, collectionview, drag-drop, indicator, styling
---

# .NET MAUI CollectionView Reorder Indicator Styling

The Reorder indicator appears while reordering an item inside the CollectionView to notify the end-user where the item can be dropped. To style the Reorder Indicator, create an implicit style and set its `TargetType` to `CollectionViewReorderIndicator`.

Check a quick example with a modified `CollectionViewReorderIndicator`:

**1.** Add the following sample implicit style to the page's resources:

<snippet id='collectionview-reorder-indicator-style' />

**2.** Add the `RadCollectionView` instance to the page:

<snippet id='collectionview-reorder-indicator-styling' />

For the purpose of the example, use the `ViewModel` and `DataModel` classes from the [Drag and Drop Overview]({%slug collectionview-draganddrop-overview%}) topic.

Check the result below:

![.NET MAUI CollectionView Reorder Indicator Styling](../images/collectionview-dragdrop-rowindicatorstyle.png)

## See Also

- [Drag and Drop Overview]({%slug collectionview-draganddrop-overview%})
- [DragVisual and ReorderIndicator Templates]({%slug collectionview-draganddrop-templates%})
- [Reorder Grouped Items]({%slug collectionview-reorder-grouped-items%})
- [Drag and Drop between CollectionViews]({%slug collectionview-drag-and-drop-between-collectionviews%})