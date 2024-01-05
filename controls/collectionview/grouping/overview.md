---
title: Overview
page_title: .NET MAUI CollectionView Documentation - Grouping
description: Review the Telerik UI for .NET MAUI CollectionView Grouping feature.
position: 0
slug: collectionview-grouping
tags: group, collectionview, grouping
---

# .NET MAUI CollectionView Grouping

The .NET MAUI CollectionView provides you with the functionality to programmatically group its data at runtime. You can programmatically group the data by adding group descriptors to the  `RadCollectionView.GroupDescriptors` collection. There are two types of descriptors:

* [PropertyGroupDescriptor]({%slug collectionview-property-group-descriptor%})&mdash;Uses a property from the model as a group key.
* [DelegateGroupDescriptor]({%slug collectionview-delegate-group-descriptor%})&mdash;This descriptor enables you to group by a custom key(for example, some complex expression combining two or more properties) instead of being limited by the value of a single property. 

## Group Header

When groupin descriptor is applied, the default group template is visualized. Review the [Group Header]({%slug collectionview-group-header%}) article to learn more about how to style and customize the group header.

## Expand and Collapse Groups

The control supports groups expand and collapse operations either through the UI by tapping on the group headers or programmatically. For more details, refer to the [Expand and Collapse Groups]({%slug listview-features-expand-collapse %}) article.

## Bindable GroupDescriptor

Users can control the `GroupDescriptor` collection by using MVVM. For more details, refer to the [Bindable Group Descriptors]({%slug listview-bindable-group-descriptor%}) article.

## Group Footer

The CollectionView has a support for group footer. You can visualize the footers by setting the `IsGroupFooterVisible` to `True`. For more details, refer to the [Group Footer]({%slug listview-bindable-group-descriptor%}) article.

## See Also

- [Filtering]({%slug listview-features-filtering%})
- [Sorting]({%slug listview-features-sorting%})
- [Selection]({%slug listview-features-selection%})
