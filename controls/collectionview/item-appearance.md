---
title: Item Appearance
page_title: .NET MAUI CollectionView Documentation - Item Appearance
description: Learn more about the item appearance in the Telerik UI for .NET MAUI CollectionView control. 
position: 2
slug: collectionview-item-appearance
---

# .NET MAUI CollectionView Define Item Appearance

The items in the CollectionView are the presentation of each data item from the control's `ItemsSource`. 

You can define the appearance of each item in the CollectionView by setting the `ItemTemplate` property.

**1.** Create a `DataModel`:

<snippet id='combobox-city-businessmodel' />

**2.** Create a `ViewModel`:

<snippet id='collectionview-selection-viewmodel' />

**3.** Define the CollectionView control with a sample `ItemTemplate`:

<snippet id='collectionview-disabled-selection' />

**4.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```				

## See Also

- [Grouping]({%slug collectionview-grouping%})
- [Filtering]({%slug collectionview-filtering%})
- [Sorting]({%slug collectionview-sorting%})
- [Selection]({%slug collectionview-selection%})
- [Commands]({%slug collectionview-commands%})
- [Events]({%slug collectionview-commands%})