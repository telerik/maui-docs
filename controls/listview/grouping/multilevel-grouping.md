---
title: Multi-Level Grouping
page_title: .NET MAUI ListView Documentation - Grouping
description: Check our &quot;Multi-Level Grouping&quot; documentation article for Telerik ListView for .NET MAUI
position: 5
slug: listview-grouping-multilevel
previous_url: /controls/listview/grouping/listview-grouping-multilevel
description: Describing RadListView grouping feature
tags: group, radlistview, groupdescriptor, multilevel
---

# Multi-Level Grouping

This article provides an overview on how you could enable multi-level grouping in the ListView.

>note Before proceeding, go through the [Grouping Overview]({%slug listview-features-grouping%}) topic.

Create the following business object:

<snippet id='listview-grouping-groupdescriptors-businessobject' />

Create a `ViewModel` class as shown below:

<snippet id='listview-grouping-groupdescriptors-viewmodel' />

To visualize the hierarchical relation between groups, add a custom `GroupHeaderTemplate` (of type `DataTemplate`) to the Resources of your page:

<snippet id='listview-grouping-multilevel-templates' />

The `LevelToMarginConverter` calculates the margin of each group header according to its Level:

<snippet id='listview-grouping-multilevel-converter' />

Add the `RadListView` definition with two `PropertyGroupDescriptors` as shown in the next snippet:

<snippet id='listview-grouping-multilevel-definition' />

Include the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
```

The following image shows the final result.

![](../images/listview_grouping_multilevel.png)

## See Also

- [Grouping]({%slug listview-features-grouping%})
- [Filtering]({%slug listview-features-filtering%})
- [Sorting]({%slug listview-features-sorting%})
