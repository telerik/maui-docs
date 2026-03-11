---
title: Filtering
page_title: .NET MAUI ListView Documentation - Filtering
description: Check the Telerik .NET MAUI ListView filtering options like programmatically filtering and using filter descriptors.
position: 7
slug: listview-features-filtering
previous_url: /controls/listview/listview-features-filtering
tags: filter, radlistview, filterdescriptor
---

@[template](/_contentTemplates/common/listview-obsolete.md#listview-obsolete)

# .NET MAUI ListView Filtering

The ListView provides the functionality to programmatically filter its data at runtime. This can be achieved through adding filter descriptors that implement the `IFilter` interface to the `RadListView.FilterDescriptors` collection. You can use our `DelegateFilterDescriptor` implementation.

## DelegateFilterDescriptor

The `DelegateFilterDescriptor` property supports a `Filter`, which defines the function used to check whether a data item passes the filter or not.

## Bindable Filter Descriptors

The `FilerDescriptors` collection of the ListView supports binding, which means that you can modify the directly descriptors directly from the `ViewModel`.

## See Also

- [Grouping]({%slug listview-features-grouping%})
- [Sorting]({%slug listview-features-sorting%})
- [Selection]({%slug listview-features-selection%})
