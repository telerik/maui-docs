---
title: Overview
page_title: .NET MAUI CollectionView Documentation - Item Swipe
description: Review the Telerik UI for .NET MAUI CollectionView Item Swipe feature.
position: 0
slug: collectionview-item-swipe-overview
tags: item-swipe, collectionview, swiping
---

# .NET MAUI CollectionView Item Swipe

.NET MAUI CollectionView provides item swipe feature&mdash;when users swipe, they reveal a designated custom view with buttons, images, etc.

The image below shows how swiping can reveal buttons on the left and right:

![.NET MAUI CollectionView Item Swipe](../images/collectionview-item-swipe.png)

## Properties

You can use the following `RadCollectionView` properties to configure the item swipe feature:

- `IsItemSwipeEnabled`(`bool`)&mdash;Indicates whether the items of the CollectionView can be swiped. The default value is `False`.
- `SwipeThreshold`(`double`)&mdash;Defines the length (in pixels) of the swipe gesture that is required to trigger the feature.
- `StartSwipeLength`(`double`)&mdash;Defines the distance that the start swiped item will be moved to and stay there until the swipe gets closed.
- `EndSwipeLength`(`double`)&mdash;Defines the distance that the end swiped item will be moved to and stay there until the swipe gets closed.
- `StartSwipeTemplate`(`DataTemplate`)&mdash;Defines the content that is visualized for a swipe-left (in vertical orientations) or a swipe-up (in horizontal orientations).
- `EndSwipeTemplate`(`DataTemplate`)&mdash;Defines the content that is visualized for a swipe-right (in vertical orientations) or a swipe-down (in horizontal orientations).

## Methods

The following `RadCollectionView` methods are related to the cell swiping feature:

- void `EndItemSwipe`(`bool` `isAnimated`)&mdash;Moves the swiped item to its default position.

Check below an example of the `CollectionView` with `StartSwipeTemplate` and `EndSwipeTemplate` defined. Through the `StartSwipeTemplate` users can update a property of the data item, and through the `EndSwipeTemplate` users can delete an item.

**1.** Add sample `StartSwipeTemplate` and `EndSwipeTemplate` DataTemplates to the page's resources:

<snippet id='collectionview-itemswipe-templates' />

**2.** Add the `CollectionView` definition with `IsItemSwipeEnabled` applied:

<snippet id='collectionview-item-swipe' />

**3.** Add the events defined in the DataTemplates:

<snippet id='collectionview-itemswipe-code' />

**4.** Add the `ViewModel` class:

<snippet id='collectionview-itemswipe-viewmodel' />

**5.** Add the business object class:

<snippet id='collectionview-itemswipe-datamodel' />

## See Also

- [Swipe Events]({%slug collectionview-item-swipe-events%})
- [Swipe Commands]({%slug collectionview-item-swipe-commands%})
