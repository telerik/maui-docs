---
title: Item Swipe Events
page_title: .NET MAUI CollectionView Documentation - Item Swipe Events
description: Review the Telerik UI for .NET MAUI CollectionView Item Swipe Events.
position: 1
slug: collectionview-item-swipe-events
tags: item-swipe, collectionview, swiping, events
---

## .NET MAUI CollectionView Swiping Events

The following `RadCollectionView` events are related to the item swiping feature:

- `SwipeStarting`&mdash;Occurs when an item is about to be swiped. The event arguments are of the `CollectionViewSwipeStartingEventArgs` type that provides the following properties:
  - `Item`(`object`)&mdash;The item that will be swiped.
  - `Cancel`(`bool`)&mdash;If you set this value to `false`, the swiping will be canceled.
- `Swiping`&mdash;Occurs while the user is swiping the item. The event arguments are of the `CollectionViewSwipingEventArgs` type that provides the following properties:
  - `Item`(`object`)&mdash;The item that is being swiped.
  - `Offset`(`double`)&mdash;The offset of the swiped item from its initial position.
- `SwipeCompleted`&mdash;Occurs when the swiping of an item is completed. The event arguments are of the `CollectionViewSwipeCompletedEventArgs` type that provides the following properties:
  - `Item`(`object`)&mdash;The item that was swiped.
  - `Offset`(`double`)&mdash;The final offset of the swiped item.

Check a simple example where the swiping events are used:

**1.** Add a `CollectionView` definition with the swiping events defined:

<snippet id='collectionview-item-swipe-events' />

**2.** Add sample `StartSwipeTemplate` and `EndSwipeTemplate` DataTemplates to the page's resources:

<snippet id='collectionview-item-swipe-events-resources' />

**3.** Add the event handlers in code-behind:

<snippet id='collectionview-itemswipe-events-code' />

**4.** Add a sample `ViewModel` class:

<snippet id='collectionview-itemswipe-viewmodel' />

**5.** Add a sample `DataModel` class:

<snippet id='collectionview-itemswipe-datamodel' />

## See Also

- [Item Swipe]({%slug collectionview-item-swipe-overview%})
- [Swipe Commands]({%slug collectionview-item-swipe-commands%})
