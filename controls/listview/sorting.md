---
title: Sorting
page_title: .NET MAUI ListView Documentation - Sorting
description: Learn more about the sorting functionality about the Telerik UI for .NET MAUI ListView control.
position: 6
slug: listview-features-sorting
previous_url: /controls/listview/listview-features-sorting
tags: sort, radlistview, sorting, sortdescriptor
---

@[template](/_contentTemplates/common/listview-obsolete.md#listview-obsolete)

# .NET MAUI ListView Sorting

The ListView can be used to sort the visualized data. This can be achieved by adding different `SortDescriptors` to its `SortDescriptors` collection. There are two types of descriptors shipped with our code.

## PropertySortDescriptor

You can sort the data by a property value from the class that defines your business items. This descriptor exposes the following properties:

- `PropertyName`&mdash;Defines the string name of the property that is used to retrieve the key to sort by.
- `SortOrder`&mdash;Specifies sort order to ascending or descending.

## DelegateSortDescriptor

This descriptor enables you to sort by a custom key (for example, some complex expression combining two or more properties) instead of being limited by the value of a single property. This descriptor exposes the following properties:

- `SortOrder`&mdash;Sets the sort order to ascending or descending.
- `Comparer`&mdash;Defines the `Compare` method used by the internal [IComparer](https://docs.microsoft.com/en-us/dotnet/api/system.collections.icomparer).

## Bindable Sort Descriptors

The `SortDescriptors` collection of the ListView supports binding, which means you can modify the sort descriptors directly from the `ViewModel`.

## See Also

- [Grouping]({%slug listview-features-grouping%})
- [Filtering]({%slug listview-features-filtering%})
- [Selection]({%slug listview-features-selection%})
