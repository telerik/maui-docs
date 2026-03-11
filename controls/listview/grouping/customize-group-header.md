---
title: Group Header Template
page_title: .NET MAUI ListView Documentation - Group Templates
description: Check the Telerik UI for .NET MAUI ListView GroupHeader's BindingContext properties and how to define a custom GroupHeaderTemplate.
position: 4
slug: listview-customize-group-header
previous_url: /controls/listview/grouping/listview-customize-group-header
tags: group, radlistview, groupdescriptor, custom group header
---

@[template](/_contentTemplates/common/listview-obsolete.md#listview-obsolete)

# .NET MAUI ListView Group Header Template

The ListView has a default group header that is displayed when grouping is applied.

The `BindingContext` of the `GroupHeader` is a complex object and it includes the following properties:

- `IsExpanded`&mdash;Defines a value indicating whether the group is currently expanded (has its child items visible).
- `Items`&mdash;Gets the child items of the group.
- `Key`&mdash;Gets the specific for the group key.
- `Level`&mdash;Gets the zero-based level (or the depth) of the group.

In addition, you can create a custom `GroupHeaderTemplate` to achieve the desired look when grouping the ListView.

## See Also

- [Filtering]({%slug listview-features-filtering%})
- [Sorting]({%slug listview-features-sorting%})
- [Selection]({%slug listview-features-selection%})
