---
title: Overview
page_title: .NET MAUI CollectionView Documentation - Grouping
description: Review the Telerik UI for .NET MAUI CollectionView Grouping feature.
position: 0
slug: collectionview-grouping
tags: group, collectionview, grouping
---

# .NET MAUI CollectionView Grouping

The .NET MAUI CollectionView provides you with the functionality to programmatically group its data at runtime. You can programmatically group the data by adding group descriptors to the  `RadCollectionView.GroupDescriptors` collection. To achieve this, use the following descriptors:

* [`CollectionViewPropertyGroupDescriptor`]({%slug collectionview-property-group-descriptor%})&mdash;Uses a property from the model as a group key.
* [`CollectionViewDelegateGroupDescriptor`]({%slug collectionview-delegate-group-descriptor%})&mdash;Enables you to group by a custom key (for example, some complex expression combining two or more properties) instead of being limited by the value of a single property. 

## Group Header

When a group descriptor is applied, the default group template is visualized. Review the [Group Header]({%slug collectionview-group-header%}) article to learn more about how to style and customize the group header.

## Expand and Collapse Groups

The control supports groups expand and collapse operations through the UI by tapping on the group headers.

## Bindable GroupDescriptor

Users can control the `GroupDescriptors` collection by using MVVM.

## Group Footer

The CollectionView has support for a group footer. You can visualize the footers by setting the `IsGroupFooterVisible` to `True`. For more details, refer to the [Group Footer]({%slug collectionview-group-footer%}) article.

## Styling the Group Header and Footer

Style the group header and the footer by setting the following properties:

* `GroupHeaderStyle` (`Style` with target type `CollectionViewGroupHeaderItemView`)&mdash;Specifies the style applied to the group header when grouping is applied.
* `GroupFooterStyle` (`Style` with target type `CollectionViewFooterItemView`)&mdash;Specifies the style applied to the footer when the `Footer` property is set and `IsFooterVisible` is set to `true`.


## See Also

- [Property Group Descriptor]({%slug collectionview-property-group-descriptor%})
- [Delegate Group Descriptor]({%slug collectionview-delegate-group-descriptor%})
- [Bindable Group Descriptors]({%slug collectionview-bindable-group-descriptor%})
- [Multi-level Grouping Descriptor]({%slug collectionview-grouping-multilevel%})
- [Group Header]({%slug collectionview-group-header%})
- [Group Footer]({%slug collectionview-group-footer%})
