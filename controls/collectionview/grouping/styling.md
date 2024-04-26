---
title: Group Styling
page_title: .NET MAUI CollectionView Documentation - Group Styles
description: Check the Telerik for .NET MAUI CollectionView styling options for the Group.
position: 10
slug: collectionview-group-styling
tags: style, group, collectionview, maui, dotnet maui
---

# .NET MAUI CollectionView Group Styling

To style the group header and the footer, set the following properties:

* `GroupContainerStyle` (`Style` with target type `RadCollectionViewGroupItem`)&mdash;Specifies the style applied to the group header when grouping is applied.

The `GroupContainerStyle` has a `ExpandCollapseIndicatorStyle` property that allows you to style the expand button. The `ExpandCollapseIndicatorStyle` (`Style` with target type `Label`).

The following example shows how to use the `GroupContainerStyle`:

**1.** Define the following business object:

<snippet id='collectionview-datamodel' />

**2.** Create a `ViewModel` class as shown below:

<snippet id='collectionview-viewmodel' />

**3.** Add the `RadCollectionView` definition with the `GroupContainerStyle` set:

<snippet id='collectionview-group-container-style' />

**4.** Include the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
```

**5.** Add the following style for the `GroupContainerStyle` to the page's resource:

<snippet id='contentview-group-container-style-resources' />

**6.** Add the following style for the `ExpandCollapseIndicatorStyle` to the page's resource:

<snippet id='collectionview-group-expand-collapse-button-resources' />

> For a runnable example demonstrating the CollectionView GroupHeader Styling, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **CollectionView > Styling**.

## See Also

- [Item Appearance]({%slug collectionview-item-appearance%})
- [Grouping]({%slug collectionview-grouping%})
- [Filtering]({%slug collectionview-filtering%})
- [Sorting]({%slug collectionview-sorting%})
- [Selection]({%slug collectionview-selection%})
- [Commands]({%slug collectionview-commands%})
- [Events]({%slug collectionview-commands%})
