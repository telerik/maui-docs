---
title: Item Swipe Commands
page_title: .NET MAUI CollectionView Documentation - Item Swipe Commands
description: Review the Telerik UI for .NET MAUI CollectionView Item Swipe Commands.
position: 2
slug: collectionview-item-swipe-commands
tags: item-swipe, collectionview, swiping, commands
---

## .NET MAUI CollectionView Swiping Commands

The .NET MAUI CollectionView provides the following commands related to swipe actions:

- `SwipeStartingCommand`(`ICommand`)&mdash;Occurs when an item is about to be swiped. The command parameter is of the `CollectionViewSwipeStartingCommandContext` type that provides the following properties:
  - `Item`(`object`)&mdash;The item that will be swiped.
  - `Cancel`(`bool`)&mdash;If you set this value to `false`, the swiping will be canceled.
- `Swiping`(`ICommand`)&mdash;Occurs while the user is swiping the item. The command parameter is of the `CollectionViewSwipingCommandContext` type that provides the following properties:
  - `Item`(`object`)&mdash;The item that is being swiped.
  - `Offset`(`double`)&mdash;The offset of the swiped item from its initial position.
- `ItemSwipeCompleted`(`ICommand`)&mdash;Occurs when the swiping of an item is completed. The command parameter is of the `CollectionViewSwipeCompletedCommandContext` type that provides the following properties:
  - `Item`(`object`)&mdash;The item that was swiped.
  - `Offset`(`double`)&mdash;The final offset of the swiped item.

Check a simple example where the swiping commands are used:

**1.** Add a `CollectionView` definition with the swiping commands defined:

<snippet id='collectionview-item-swipe-commands' />

**2.** Add sample `StartSwipeTemplate` and `EndSwipeTemplate` DataTemplates to the page's resources:

<snippet id='collectionview-item-swipe-commands-resources' />

**3.** Add a sample `ViewModel` class with the commands:

<snippet id='collectionview-itemswipe-commands-viewmodel' />

**5.** Add a sample `DataModel` class:

<snippet id='collectionview-itemswipe-datamodel' />

## See Also

- [Item Swipe]({%slug collectionview-item-swipe-overview%})
- [Swipe Events]({%slug collectionview-item-swipe-events%})
