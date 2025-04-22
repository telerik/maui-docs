---
title: Programmatically Unswiping an Item in CollectionView
description: Learn how to unswipe an item in CollectionView for .NET MAUI programmatically using the EndItemSwipe method.
type: how-to
page_title: How to Unswipe an Item Programmatically in RadCollectionView for .NET MAUI
slug: unswipe-item-collectionview
tags: collectionview, .net maui, unswipe, item, programmatically
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.1.0 | Telerik UI for .NET MAUI CollectionView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

In scenarios where an item in the CollectionView is swiped, there might be a need to programmatically return it to its original position. 

This knowledge base article also answers the following questions:

- How can I programmatically close a swiped item in `RadCollectionView`?
- What method is used to unswipe an item in `RadCollectionView`?
- Is there a way to programmatically reset the swipe state of an item in RadCollectionView?

## Solution

To programmatically unswipe an item in RadCollectionView, use the `EndItemSwipe()` method. This method reverts a swiped item back to its original position.

Here is a simple example of how to use the `EndItemSwipe()` method:

```csharp
// Assuming you have an instance of RadCollectionView named 'collectionView'
collectionView.EndItemSwipe();
```

For more detailed information about item swipe functionality, including the `EndItemSwipe()` method, refer to the [CollectionView Item Swipe Overview](https://docs.telerik.com/devtools/maui/controls/collectionview/item-swipe/overview#methods).

## See Also

- [CollectionView Overview]({%slug collectionview-overview%})
- [Item Swipe in RadCollectionView](https://docs.telerik.com/devtools/maui/controls/collectionview/item-swipe/overview)
