---
title: DragVisual and DropIndicator Templates
page_title: .NET MAUI CollectionView Documentation - DragVisual and DropIndicator Templates
description: Review the Telerik UI for .NET MAUI CollectionView DragVisual and DropIndicator Templates.
position: 3
slug: collectionview-dragdrop-templates
tags: reorder, collectionview, drag-drop, templates, dragvisual, dropindicator
---

# .NET MAUI CollectionView DragVisual &amp; DropIndicator Templates

The CollectionView provides the following templates for customizing the drag cue during a drag-and-drop operation as well as the indicator where the dragged item will be dropped:

* `DragVisualTemplate`(`DataTemplate`)&mdash;Represents the drag visual of the dragged item during a drag-and-drop operation.
* `DropIndicatorTemplate`(`DataTemplate`)&mdash;Represents the indicator shown between the CollectionView items during a drag-and-drop operation which shows where the dragged item will be dropped.

Check an example of the CollectionView with sample `DragVisualTemplate` and `DropIndicatorTemplate`:

**1.** Add a sample DataTemplate for the drop indicator to the page's resources:

<snippet id='collectionview-dragdrop-templates-indicatortemplate' />

**2.** Add a sample DataTemplate for the drag visual to the page's resources:

<snippet id='collectionview-dragdrop-templates-dragvisual' />

**3.** Add the `RadCollectionView` definition with the `DragVisualTemplate` and `DropIndicatorTemplate` set to the previously defined templates:

<snippet id='collectionview-dragdrop-templates' />

For the purpose of the example, use the `ViewModel` and `DataModel` classes from the [Drag and Drop Overview]({%slug collectionview-dragdrop-overview%}) page.

Check the result below:

![.NET MAUI CollectionView DragVisual and DropIndicator Templates](../images/collectionview-dragdrop-templates.png)

## See Also

- [Drag and Drop Overview]({%slug collectionview-dragdrop-overview%})
- [Drag and Drop Grouped Items]({%slug collectionview-dragdrop-grouped-items%})
- [Drop Indicator Styling]({%slug collectionview-drop-indicator-styling%})
