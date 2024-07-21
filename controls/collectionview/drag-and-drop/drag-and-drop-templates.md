---
title: DragVisual and ReorderIndicator Templates
page_title: .NET MAUI CollectionView Documentation - DragVisual and ReorderIndicator Templates
description: Review the Telerik UI for .NET MAUI CollectionView DragVisual and ReorderIndicator Templates.
position: 3
slug: collectionview-draganddrop-templates
tags: reorder, collectionview, drag-drop, templates
---

# .NET MAUI CollectionView DragVisual &amp; ReorderIndicator Templates

The CollectionView provides the following templates for customizing the drag cue during a drag and drop operation as well as the indicator where the dragged item will be dropped:

* `DragVisualTemplate`(`DataTemplate`)&mdash;Represents the drag visual of the dragged item during a drag and drop operation.
* `ReorderIndicatorTemplate`(`DataTemplate`)&mdash;Represents the indicator shown between the CollectionView items during reorder.

Check an example of the CollectionView with sample `DragVisualTemplate` and `ReorderIndicatorTemplate`:

**1.** Add a sample DataTemplate for the reorder indicator to the page's resources:

<snippet id='collectionview-reorder-templates-indicatortemplate' />

**2.** Add a sample DataTemplate for the drag visual to the page's resources:

<snippet id='collectionview-reorder-templates-dragvisual' />

**3.** Add the `RadCollectionView` definition with the `DragVisualTemplate` and `ReorderIndicatorTemplate` set to the previously defined templates:

<snippet id='collectionview-reorder-templates' />

For the purpose of the example, use the `ViewModel` and `DataModel` classes from the [Drag and Drop Overview]({%slug collectionview-draganddrop-overview%}) topic.

Check the result below:

![.NET MAUI CollectionView DragVisual and ReorderIndicator Templates](../images/collectionview-dragdrop-templates.png)

## See Also

- [Drag and Drop Overview]({%slug collectionview-draganddrop-overview%})
- [Reorder Grouped Items]({%slug collectionview-reorder-grouped-items%})
- [Reorder Indicator Styling]({%slug collectionview-reorder-indicator-styling%})