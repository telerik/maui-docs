---
title: Delegate Group Descriptor
page_title: .NET MAUI ListView Documentation - Grouping
description: Review the Telerik UI for .NET MAUI ListView DelegateGroupDescriptor option which enables you to group by a custom key.
position: 2
slug: listview-delegate-group-descriptor
previous_url: /controls/listview/grouping/listview-delegate-group-descriptor
tags: group, radlistview, groupdescriptor
---

# .NET MAUI ListView Delegate Group Descriptor

DelegateGroup descriptor enables you to group by a custom key (for example, some complex expression combining two or more properties) instead of being limited by the value of a single property. This descriptor exposes the following properties:

- `KeyExtractor`&mdash;Defines the `(Func<object, object)` delegate which returns the property to retrieve the group key for each data item.
- `SortOrder`&mdash;Defines the sort order in each group to Ascending or Descending.

Let's use the same example from the previous section, and add `DelegateGroupDescriptor` through code instead.

**1.** Define the `RadListView`:

<snippet id='listview-grouping-delegategroupdescriptor' />

**2.** Include the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
```

**3.** Create and apply a delegate for grouping the items (for example by their first letter) as following:

<snippet id='listview-grouping-delegategroupdescriptor-settingdelegate' />

**4.** Add a business model:

<snippet id='listview-grouping-groupdescriptors-businessobject' />

**5.** Add a `ViewModel` with a collection of Cities:

<snippet id='listview-grouping-groupdescriptors-viewmodel' />

The following image shows a ListView grouped through the `DelegateGroupDescriptor`.

![.NET MAUI ListView Grouping](../images/listview_grouping_delegatedescriptor.png)

> For the ListView DelegateGroupDescriptor example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to ListView  -> Grouping category.

## See Also

- [Filtering]({%slug listview-features-filtering%})
- [Sorting]({%slug listview-features-sorting%})
- [Selection]({%slug listview-features-selection%})
