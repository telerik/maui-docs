---
title: Filtering
page_title: .NET MAUI CollectionView Documentation - Filtering
description: Check the Telerik .NET MAUI CollectionView filtering options like programmatically filtering and using filter descriptors.
position: 12
slug: collectionview-filtering
tags: filter, radlistview, filterdescriptor
---

# .NET MAUI CollectionView Filtering

The CollectionView provides the functionality to programmatically filter its data at runtime. 

You can achieve this by adding filter descriptors that implement the `IFilter` interface to the `RadCollectionView.FilterDescriptors` collection. 

The following example implements a `CollectionViewDelegateFilterDescriptor` and uses a [`RadEntry`]({%slug entry-overview%}) control that allows the user to enter a string of text to filter the CollectionView data.

**1.** Define the `RadCollectionView` and `RadEntry` in XAML:

<snippet id='collectionview-delegate-filter-descriptor'/>

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Create a sample `DataModel`:

<snippet id='collectionview-datamodel' />

**4.** Define the `ViewModel` class:

<snippet id='collectionview-viewmodel' />

> For a runnable demo with the CollectionView Filtering example, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **CollectionView > Filtering** category.

## Bindable Filter Descriptors

The `FilerDescriptors` collection of the CollectionView supports binding, which means that you can modify the descriptors directly from the `ViewModel`.

## See Also

- [Grouping]({%slug collectionview-grouping%})
- [Sorting]({%slug collectionview-sorting%})
- [Selection]({%slug collectionview-selection%})
- [Commands]({%slug collectionview-commands%})