---
title: Delegate Group Descriptor
page_title: .NET MAUI CollectionView Documentation - Delegate Group Descriptor
description: Review the Telerik UI for .NET MAUI CollectionView DelegateGroupDescriptor option which enables you to group by a custom key.
position: 5
slug: collectionview-delegate-group-descriptor
tags: group, collectionview, groupdescriptor, dotnet maui, maui, grouping items
---

# .NET MAUI CollectionView Delegate Group Descriptor

The difference between the `DelegateGroupDescriptor` and the [PropertyGroupDescriptor]({%slug collectionview-property-group-descriptor%}) is that the `DelegateGroupDescriptor` groups data by a custom key, while the `PropertyGroupDescriptor` groups by a defined key which is a property from the model.

This descriptor exposes the following properties:

- `KeyLookup`&mdash;Defines the `IKeyLookup` instance that is used to retrieve the group key for each data item.
- `SortOrder`(enum of type `Telerik.Maui.Controls.Data.SortOrder`)&mdash;Specifies the sort order of the grouped items. The available options are: `Ascending` or `Descending`.

The following example demonstrates how to group the items in the CollectionView by using the `DelegateGroupDescriptor`.
 
**1.** Define the following business object:

<snippet id='collectionview-datamodel' />

**2.** Create a `ViewModel` class as shown below:

<snippet id='collectionview-viewmodel' />

**3.** Add the `RadCollectionView` definition with `DelegateGroupDescriptor`:

<snippet id='collectionview-delegate-group-descriptor' />

**4.** Include the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
```

**5.** Define the Custom IKeyLookup:

<snippet id='collectionview-delegate-grouping-keyextractor-function' />

**5.** Add the `DelegateGroupDescriptor` to the `RadCollectionView`:

<snippet id='collectionview-delegate-grouping' />

> For a runnable demo with the CollectionView DelegateGroupDescriptor, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Calendar > Grouping** category.

## See Also

- [Property Group Descriptor]({%slug collectionview-property-group-descriptor%})
- [Multi-level Grouping Descriptor]({%slug collectionview-grouping-multilevel%})
- [Group Header]({%slug collectionview-group-header%})