---
title: GroupStyle Selector
page_title: .NET MAUI CollectionView Documentation - GroupStyle Selector
description: The CollectionView exposes a conditional styling feature that allows you to apply different styles to each group depending on a specific condition.
position: 1
slug: collectionview-group-style-selector
---

# .NET MAUI CollectionView Group Style Selector

The .NET MAUI CollectionView exposes a conditional styling feature that allows you to apply different styles to each group header and footer depending on a specific condition.

Apply conditional styling to the group header and group footer by setting the following properties:

* `GroupHeaderStyleSelector`(`Style` with target type `CollectionViewGroupHeaderItemView`)&mdash;Specifies the style applied to the group header when grouping is applied.
* `GroupFooterStyleSelector`(`Style` with target type `CollectionViewGroupFooterItemView`)&mdash;Specifies the style applied to the group footer when `Footer` property is set and `IsGroupFooterVisible` is set to `true`.

The following example shows how to use the `ItemStyleSelector`:

**1.** Define the following business object:

<snippet id='collectionview-datamodel' />

**2.** Create a `ViewModel` class as shown below:

<snippet id='collectionview-viewmodel' />

**3.** Add the `RadCollectionView` definition with the `GroupHeaderStyleSelector` and `GroupFooterStyleSelector` set:

<snippet id='collectionview-group-style-selector' />

**4.** Include the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
```

**5.** Add the following styles to the page's resource for `GroupHeaderStyleSelector`:

<snippet id='collectionview-group-header-styleselector' />

**6.**  Add the following styles to the page's resource for `GroupFooterStyleSelector`:

<snippet id='collectionview-group-footer-styleselector' />

> For a runnable example demonstrating the TreeView ItemStyleSelector, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **CollectionView > Styling**.

## See Also

- [Item Appearance]({%slug collectionview-item-appearance%})
- [Grouping]({%slug collectionview-grouping%})
- [Filtering]({%slug collectionview-filtering%})
- [Sorting]({%slug collectionview-sorting%})
- [Selection]({%slug collectionview-selection%})
- [Commands]({%slug collectionview-commands%})
- [Events]({%slug collectionview-commands%})