---
title: GroupStyle Selector
page_title: .NET MAUI CollectionView Documentation - GroupStyle Selector
description: The CollectionView exposes a conditional styling feature that allows you to apply different styles to each group depending on a specific condition.
position: 11
slug: collectionview-group-style-selector
---

# .NET MAUI CollectionView Group Style Selector

The .NET MAUI CollectionView component exposes a conditional styling feature that allows you to apply different styles to each group header and footer depending on a specific condition.

Apply conditional styling to the group header and group footer by setting the following properties:

* `GroupViewStyleSelector` (`Style` with target type `RadCollectionViewGroupItem`)&mdash;Specifies the style applied to the group container when grouping is applied.

The following example shows how to use the `GroupViewStyleSelector`:

**1.** Define the following business object:

<snippet id='collectionview-datamodel' />

**2.** Create a `ViewModel` class as shown below:

<snippet id='collectionview-viewmodel' />

**3.** Add the `RadCollectionView` definition with the `GroupViewStyleSelector` set:

<snippet id='collectionview-groupview-styleselector' />

**4.** Include the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
```

**5.** Add the following styles to the page's resource for `GroupViewStyleSelector`:

<snippet id='collectionview-group-styleselector-resources' />

**6.** Implement the conditional styling:

<snippet id='collectionview-grouping-styleselector' />

> For a runnable example demonstrating the CollectionView GroupView StyleSelectors, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **CollectionView > Styling** category.

## See Also

- [Grouping]({%slug collectionview-grouping%})
- [Filtering]({%slug collectionview-filtering%})
- [Sorting]({%slug collectionview-sorting%})
- [Selection]({%slug collectionview-selection%})
- [Commands]({%slug collectionview-commands%})
- [Events]({%slug collectionview-commands%})