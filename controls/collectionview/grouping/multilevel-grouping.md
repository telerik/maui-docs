---
title: Multi-Level Grouping
page_title: .NET MAUI CollectionView Documentation - Grouping
description: Review the Telerik UI for .NET MAUI CollectionView Multi-Level Grouping feature and how to enable it. 
position: 5
slug: collectionview-grouping-multilevel
tags: group, collectionview, groupdescriptor, multilevel, nested grouping, maui, dotnet maui
---

# .NET MAUI CollectionView Multi-Level Grouping

This article demonstrates how to enable multi-level grouping in the CollectionView control. The sample implementation below uses multiple `CollectionViewPropertyGroupDescriptor` definitions:

**1.** Define the following business object:

<snippet id='collectionview-datamodel' />

**2.** Create a `ViewModel` class as shown below:

<snippet id='collectionview-viewmodel' />

**3.** Add the `RadCollectionView` definition with two `PropertyGroupDescriptors` as shown in the next snippet:

<snippet id='collectionview-multilevel-grouping' />

**4.** Include the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
```

The following image shows the final result.

![.NET MAUI CollectionView Multi-Level Grouping]()

> For a runnable demo with the CollectionView Multi-Level Grouping, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **CollectionView > Grouping** category.

## See Also

- [PropertyGroup Descriptor]({%slug collectionview-property-group-descriptor%})
- [Delegate Group Descriptor]({%slug collectionview-delegate-group-descriptor%})
- [Bindable Group Descriptors]({%slug collectionview-bindable-group-descriptor%})
- [Group Header]({%slug collectionview-group-header%})
- [Group Footer]({%slug collectionview-group-footer%})

