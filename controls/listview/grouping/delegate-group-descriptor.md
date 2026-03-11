---
title: Delegate Group Descriptor
page_title: .NET MAUI ListView Documentation - Grouping
description: Review the Telerik UI for .NET MAUI ListView DelegateGroupDescriptor option which enables you to group by a custom key.
position: 2
slug: listview-delegate-group-descriptor
previous_url: /controls/listview/grouping/listview-delegate-group-descriptor
tags: group, radlistview, groupdescriptor
---

@[template](/_contentTemplates/common/listview-obsolete.md#listview-obsolete)

# .NET MAUI ListView Delegate Group Descriptor

DelegateGroup descriptor enables you to group by a custom key (for example, some complex expression combining two or more properties) instead of being limited by the value of a single property. This descriptor exposes the following properties:

- `KeyExtractor`&mdash;Defines the `(Func<object, object)` delegate which returns the property to retrieve the group key for each data item.
- `SortOrder`&mdash;Defines the sort order in each group to Ascending or Descending.

## See Also

- [Filtering]({%slug listview-features-filtering%})
- [Sorting]({%slug listview-features-sorting%})
- [Selection]({%slug listview-features-selection%})
