---
title: ItemStyle Selector
page_title: .NET MAUI CollectionView Documentation - ItemStyle Selector
description: The CollectionView exposes a conditional styling feature that allows you to apply different styles to each item depending on a specific condition.
position: 1
slug: collectionview-itemstyle-selector
---

# .NET MAUI CollectionView Item Style Selector

The .NET MAUI CollectionView exposes a conditional styling feature that allows you to apply different styles to each item depending on a specific condition.

![.NET MAUI CollectionView Item Style Selector](images/collectionview-itemstyle-selector.png)

The following example shows how to use the `ItemViewStyleSelector`:

**1.** Define the following business object:

<snippet id='collectionview-datamodel' />

**2.** Create a `ViewModel` class as shown below:

<snippet id='collectionview-viewmodel' />

**3.** Add the `RadCollectionView` definition with the `ItemViewStyleSelector` set:

<snippet id='collectionview-itemview-styleselector' />

**4.** Include the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
```

**5.** Add the following styles to the page's resource:

<snippet id='collectionview-itemview-styleselector-resources' />

**6.** Implement the conditional styling:

<snippet id='collectionview-styleselector' />

> For a runnable example demonstrating the CollectionView ItemView StyleSelector, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **CollectionView > Styling** category.

## See Also

- [Item Appearance]({%slug collectionview-item-appearance%})
- [Grouping]({%slug collectionview-grouping%})
- [Filtering]({%slug collectionview-filtering%})
- [Sorting]({%slug collectionview-sorting%})
- [Selection]({%slug collectionview-selection%})
- [Commands]({%slug collectionview-commands%})
- [Events]({%slug collectionview-commands%})