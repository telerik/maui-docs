---
title: Delegate Group Descriptor
page_title: .NET MAUI CollectionView Documentation - Delegate Group Descriptor
description: Review the Telerik UI for .NET MAUI CollectionView DelegateGroupDescriptor option which enables you to group by a custom key.
position: 2
slug: collectionview-delegate-group-descriptor
tags: group, collectionview, groupdescriptor, dotnet maui, maui, grouping items
---

# .NET MAUI CollectionView Delegate Group Descriptor

The `CollectionViewDelegateGroupDescriptor` enables you to group by a custom key (for example, some complex expression combining two or more properties) instead of being limited by the value of a single property. This descriptor exposes the following properties:

- `KeyExtractor`&mdash;Defines the `(Func<object, object)` delegate which returns the property to retrieve the group key for each data item.
- `SortOrder`(enum of type `Telerik.Maui.Controls.CollectionView.CollectionViewSortOrder`)&mdash;Specifies the sort order of the grouped items. The available options are: `Ascending` or `Descending`.

## Example with CollectionViewPropertyGroupDescriptor
 
**1.** Define the following business object:

<snippet id='collectionview-datamodel' />

**2.** Create a `ViewModel` class as shown below:

<snippet id='collectionview-viewmodel' />

**3.** Add the `RadCollectionView` definition with `CollectionViewDelegateGroupDescriptor`:

<snippet id='collectionview-property-group-descriptor' />

**4.** Include the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
```

> For a runnable demo with the CollectionView DelegateGroupDescriptor, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Calendar > Grouping** category.

## See Also

- [Property Group Descriptor]({%slug collectionview-property-group-descriptor%})
- [Bindable Group Descriptors]({%slug collectionview-bindable-group-descriptor%})
- [Multi-level Grouping Descriptor]({%slug collectionview-grouping-multilevel%})
- [Group Header]({%slug collectionview-group-header%})
- [Group Footer]({%slug collectionview-group-footer%})