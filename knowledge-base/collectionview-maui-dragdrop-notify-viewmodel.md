---
title: Using the Drop Method in DragDropBehavior with CollectionView for .NET MAUI
description: Learn how to notify the view model about drag-and-drop actions in CollectionView for .NET MAUI using the Drop method in DragDropBehavior.
type: how-to
page_title: Handling DragDropBehavior in CollectionView for .NET MAUI
slug: collectionview-maui-dragdrop-notify-viewmodel
tags: collectionview, .net maui, dragdropbehavior, drop-method, viewmodel
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.1.0 | Telerik UI for .NET MAUI CollectionView |[Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 


## Description

I want to notify the view model when drag-and-drop actions are performed in the [CollectionView for .NET MAUI](https://docs.telerik.com/devtools/maui/controls/collectionview/overview). Unlike `RadListView.ReorderEnded` event, CollectionView uses `DragDropBehavior`, but it isn't clear how to inform the view model of the drop action. 

This knowledge base article also answers the following questions:
- How to handle drag-and-drop in CollectionView for .NET MAUI?
- How to use the `Drop` method of `DragDropBehavior` in CollectionView?
- How to notify a view model of drag-and-drop actions in CollectionView for .NET MAUI?

## Solution

To notify the view model of drag-and-drop actions in the CollectionView for .NET MAUI, use the `Drop` method in the `DragDropBehavior`. This method is triggered when an item is dropped. You can call this method within the context of the behavior to handle the drag-and-drop operation.

### Example
Here is an example of implementing the `Drop` method:

```csharp
public class CustomDragDropBehavior : CollectionViewDragDropBehavior
{
    public override void Drop(CollectionViewDragDropContext state)
    {
        var collectionView = this.CollectionView;
        if (collectionView != null)
        {
            base.Drop(state);
            // Notify the view model about the drop action
            var viewModel = collectionView.BindingContext as YourViewModel;
            // add your logic here
        }
    }
}
```

### Key Points

1. Override the `Drop` method in a custom behavior class.
2. Access the `CollectionView`.
3. Notify the view model by invoking a method or updating properties.

For additional information on drag-and-drop functionality, refer to the [DragDrop Grouped Items documentation](https://docs.telerik.com/devtools/maui/controls/collectionview/drag-and-drop/dragdrop-grouped-items).

## See Also

- [CollectionView Drag-and-Drop Overview](https://docs.telerik.com/devtools/maui/controls/collectionview/drag-and-drop/overview)
