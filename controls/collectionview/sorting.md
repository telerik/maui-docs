---
title: Sorting
page_title: .NET MAUI CollectionView Documentation - Sorting
description: Learn more about the sorting functionality in the Telerik UI for .NET MAUI CollectionView control.
position: 9
slug: collectionview-sorting
tags: sort, collectionview, sorting, sortdescriptor
---

# .NET MAUI CollectionView Sorting

The CollectionView control allows you to sort the visualized data. To configure the Sorting feature, add different `SortDescriptors` to the `SortDescriptors` collection of the CollectionView.

## Property Sort Descriptor

You can sort the data by a property value from the class that defines your business items. The `CollectionViewPropertySortDescriptor` exposes the following properties:

- `PropertyName`&mdash;Defines the string name of the property that is used to retrieve the key to sort by.
- `SortOrder`&mdash;Specifies sort order to ascending or descending.

The following example demonstrates how to define the CollectionViewPropertySortDescriptor.

**1.** Define the `RadCollectionView` in XAML:

<snippet id='collectionview-property-sort-descriptor'/>

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Create a sample `DataModel`:

<snippet id='collectionview-datamodel' />

**4.** Define the `ViewModel` class:

<snippet id='collectionview-viewmodel' />

> For a runnable demo with the CollectionView Sorting example, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **CollectionView > Sorting** category.

## Delegate Sort Descriptor

The `CollectionViewDelegateSortDescriptor` enables you to sort by a custom key (for example, a complex expression combining two or more properties) and avoid being limited by the value of a single property. This descriptor exposes the following properties:

- `SortOrder`&mdash;Sets the sort order to ascending or descending.
- `Comparer`&mdash;Defines the `Compare` method used by the internal [`IComparer`](https://docs.microsoft.com/en-us/dotnet/api/system.collections.icomparer).

## Bindable Sort Descriptors

The `SortDescriptors` collection of the CollectionView supports binding, which means you can modify the sort descriptors directly from the view model.

## See Also

- [Grouping]({%slug collectionview-grouping%})
- [Filtering]({%slug collectionview-filtering%})
- [Selection]({%slug collectionview-selection%})
