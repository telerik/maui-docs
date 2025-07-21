---
title: Current Item
page_title: .NET MAUI CollectionView Documentation - Current Item
description: Learn how to set the behavior and style the appearance of the current cell of the Telerik UI for .NET MAUI CollectionView component.
position: 15
slug: collectionview-current-item
tags: current item, keyboard navigation, maui, collectionview, dotnet maui
---

# .NET MAUI CollectionView Current Item

The [Telerik UI for .NET MAUI CollectionView]({%slug collectionview-overview%}) provides options for configuring the behavior and style of its current item. 

## Setting the Behavior

The CollectionView allows you to use the `CurrentItem` property of type `object` to programmatically modify the current item during keyboard navigation, when using the mouse, and so on.

The `RadCollectionViewItemView` exposes a read-only property `IsCurrent` (`bool`) which gets the value indicating whether the view is visualized as current during keyboard navigation. The property returns `true` when the border of the current item is visualized.

Access the `RadCollectionViewItemView` through the [`ItemViewStyle`]({%slug collectionview-item-styling%}).

## Styling the Item

You can style the current item by setting the `Focused`, `FocusedSelected`, and `FocusedMouseOver` [visual states of the CollectionView]({%slug collectionview-visual-states%}). Define the visual states by using the [Item Styling of the CollectionView]({%slug collectionview-item-styling%}).

## Additional Resources

- [.NET MAUI CollectionView Product Page](https://www.telerik.com/maui-ui/collectionview)
- [.NET MAUI CollectionView Forum Page](https://www.telerik.com/forums/maui?tagId=1829)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Data Binding]({%slug collectionview-data-binding%})
- [Grouping]({%slug collectionview-grouping%})
- [Filtering]({%slug collectionview-filtering%})
- [Sorting]({%slug collectionview-sorting%})
- [Selection]({%slug collectionview-selection%})
- [Commands]({%slug collectionview-commands%})
- [Events]({%slug collectionview-events%})