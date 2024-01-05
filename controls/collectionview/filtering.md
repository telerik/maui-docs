---
title: Filtering
page_title: .NET MAUI CollectionView Documentation - Filtering
description: Check the Telerik .NET MAUI CollectionView filtering options like programmatically filtering and using filter descriptors.
position: 7
slug: collectionview-filtering
tags: filter, radlistview, filterdescriptor
---

# .NET MAUI CollectionView Filtering

The CollectionView provides the functionality to programmatically filter its data at runtime. This can be achieved through adding filter descriptors that implement the `IFilter` interface to the `RadCollectionView.FilterDescriptors` collection. You can use the `CollectionViewDelegateFilterDescriptor` implementation.

## CollectionView Delegate Filter Descriptor



## Bindable Filter Descriptors

The `FilerDescriptors` collection of the CollectionView supports binding, which means that you can modify the directly descriptors directly from the `ViewModel`.


![.NET MAUI CollectionView Filter Descriptors MVVM](images/listview-features-bindable-filter.png)

## See Also

