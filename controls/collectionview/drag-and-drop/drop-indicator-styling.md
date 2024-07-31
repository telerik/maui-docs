---
title: Drop Indicator Styling
page_title: .NET MAUI CollectionView Documentation - Drop Indicator Styling
description: Review the Telerik UI for .NET MAUI CollectionView Drop Indicator Styling.
position: 4
slug: collectionview-drop-indicator-styling
tags: reorder, collectionview, drag-drop, indicator, styling
---

# .NET MAUI CollectionView Drop Indicator Styling

The drop indicator appears while dragging an item inside the CollectionView to notify the end user where the item can be dropped. To style the drop indicator, create an implicit style and set its `TargetType` to `CollectionViewDropIndicator`.

Check a quick example with a modified `CollectionViewDropIndicator`:

**1.** Add the following sample implicit style to the page's resources:

<snippet id='collectionview-drop-indicator-style' />

**2.** Add the `RadCollectionView` instance to the page:

<snippet id='collectionview-drop-indicator-styling' />

For the purpose of the example, use the `ViewModel` and `DataModel` classes from the [Drag and Drop Overview]({%slug collectionview-draganddrop-overview%}) topic.

Check the result below:

![.NET MAUI CollectionView Drop Indicator Styling](../images/collectionview-dragdrop-dropindicatorstyle.png)

## See Also

- [Drag and Drop Overview]({%slug collectionview-dragdrop-overview%})
- [DragVisual and DropIndicator Templates]({%slug collectionview-dragdrop-templates%})
- [Drag and Drop Grouped Items]({%slug collectionview-dragdrop-grouped-items%})
- [Drag and Drop between CollectionViews]({%slug collectionview-dragdrop-between-collectionviews%})
