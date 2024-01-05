---
title: Sorting
page_title: .NET MAUI CollectionView Documentation - Sorting
description: Learn more about the sorting functionality about the Telerik UI for .NET MAUI CollectionView control.
position: 6
slug: collectionview-sorting
tags: sort, collectionview, sorting, sortdescriptor
---

# .NET MAUI CollectionView Sorting

The CollectionView can be used to sort the visualized data. This can be achieved by adding different `SortDescriptors` to its `SortDescriptors` collection.

## CollectionView PropertySortDescriptor

You can sort the data by a property value from the class that defines your business items. The `CollectionViewPropertySortDescriptor` descriptor exposes the following properties:

- `PropertyName`&mdash;Defines the string name of the property that is used to retrieve the key to sort by.
- `SortOrder`&mdash;Specifies sort order to ascending or descending.

## CollectionView DelegateSortDescriptor

The `CollectionViewDelegateSortDescriptor` enables you to sort by a custom key (for example, some complex expression combining two or more properties) instead of being limited by the value of a single property. This descriptor exposes the following properties:

- `SortOrder`&mdash;Sets the sort order to ascending or descending.
- `Comparer`&mdash;Defines the `Compare` method used by the internal [IComparer](https://docs.microsoft.com/en-us/dotnet/api/system.collections.icomparer).

![.NET MAUI CollectionView Sort Descriptor MVVM](images/collectionview-sort.png)

## Bindable Sort Descriptors

## See Also

- [Grouping]({%slug collectionview-grouping%})
- [Filtering]({%slug collectionview-filtering%})
- [Selection]({%slug collectionview-selection%})
