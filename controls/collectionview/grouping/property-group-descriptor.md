---
title: Property Group Descriptor
page_title: .NET MAUI CollectionView Documentation - Porperty Group Descriptors
description: Try now the Telerik UI for .NET MAUI CollectionView and its PropertyGroupDescriptor option for grouping items by a property value from the class that defines them.
position: 1
slug: collectionview-property-group-descriptor
tags: group, collectionview, groupdescriptor
---

# .NET MAUI CollectionView Property Group Descriptor

You can group the data by a property value from the class that defines your items. To enable this grouping, the `CollectionViewPropertyGroupDescriptor` exposes the following properties:

- `PropertyName`&mdash;Defines the string name of the property you want to group by.
- `SortOrder`(enum of type `Telerik.Maui.Controls.CollectionView.CollectionViewSortOrder`)&mdash;Specifies the sort order of the grouped items. The available options are: `Ascending` or `Descending`.

The following example demonstrates how to group the items in the CollectionView by using the `CollectionViewPropertyGroupDescriptor`.
 
**1.** Define the following business object:

<snippet id='collectionview-datamodel' />

**2.** Create a `ViewModel` class as shown below:

<snippet id='collectionview-viewmodel' />

**3.** Add the `RadCollectionView` definition with `CollectionViewPropertyGroupDescriptor`:

<snippet id='collectionview-property-group-descriptor' />

**4.** Include the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
```

> For a runnable demo with the CollectionView PropertyGroupDescriptor, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Calendar > Grouping** category.

## See Also

- [Delegate Group Descriptor]({%slug collectionview-delegate-group-descriptor%})
- [Bindable Group Descriptors]({%slug collectionview-bindable-group-descriptor%})
- [Multi-level Grouping Descriptor]({%slug collectionview-grouping-multilevel%})
- [Group Header]({%slug collectionview-group-header%})
- [Group Footer]({%slug collectionview-group-footer%})