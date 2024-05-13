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

* [`PropertyGroupDescriptor`]({%slug collectionview-property-group-descriptor%})&mdash;Uses a property from the model as a group key.
* [`DelegateGroupDescriptor`]({%slug collectionview-delegate-group-descriptor%})&mdash;Enables you to group by a custom key (for example, some complex expression combining two or more properties) instead of being limited by the value of a single property. 

![.NET MAUI CollectionView Grouping](../images/collectionview-grouping.gif "Telerik .NET MAUI CollectionView")

## Group Header

When a group descriptor is applied, the default group template is visualized. Review the [Group Header]({%slug collectionview-group-header%}) article to learn more about how to style and customize the group header.

## Expand and Collapse Groups

The control supports groups expand and collapse operations through the UI by tapping on the group headers.

## Bindable GroupDescriptor

Users can control the `GroupDescriptors` collection by using MVVM.

## Styling the Group Header 

Style the group header by setting the following properties:

* `GroupContainerStyle` (`Style` with target type `RadCollectionViewGroupItem`)&mdash;Specifies the style applied to the group header when grouping is applied.

## See Also

- [Property Group Descriptor]({%slug collectionview-property-group-descriptor%})
- [Delegate Group Descriptor]({%slug collectionview-delegate-group-descriptor%})
- [Multi-level Grouping Descriptor]({%slug collectionview-grouping-multilevel%})
- [Group Header]({%slug collectionview-group-header%})
