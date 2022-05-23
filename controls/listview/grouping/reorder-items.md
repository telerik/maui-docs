---
title: Reorder Items in Grouped ListView
page_title: .NET MAUI ListView Documentation | Reorder Items in Grouped ListView
description: Check our &quot;Reorder Items in Grouped ListView&quot; documentation article for Telerik ListView for .NET MAUI.
position: 4
slug: listview-grouping-reorderitems
previous_url: /controls/listview/grouping/listview-grouping-reorderitems
description: Describing how to handle reordering in grouped ListView
tags: group, radlistview, reordering
---

# Reorder Items in Grouped ListView

This help topic will provide an overview on how you could enable reordering feature of the ListView control when its items are grouped.

>tip Before proceeding, check the [Reorder Items]({%slug listview-features-reorder-items%}) topic which describes in details the reordering functionality of the ListView.

When the items of the ListView are grouped by certain criteria and the end user drags/starts reordering an item, the dragged item can be added to a different group. Since this depends on the items' relation, to handle the scenario, you need to subscribe to the ListView `Reorder` command and manually update the dragged item details.

The `ReorderEndedCommandContext` gives you access to the following properties:

* `Item`&mdash;Refers to the data item that is being interacted with.
* `DestinationItem`&mdash;Refers to the data item that corresponds to the location where the dragged item has been released.
* `Group`&mdash;Gets the group containing the data item that is being interacted with.
* `DestinationGroup`&mdash;Refers to the group that corresponds to the location where the dragged item has been released.
* `Placement` (of type `ItemReorderPlacement`)&mdash;Indicates whether the dragged item should be placed before or after the destination item.

Below you can find a sample implementation.

The `RadListView` definition with the `PropertyGroupDescriptor` and `Reorder` command applied:

<snippet id='listview-grouping-reorderitems-xaml' />

Include the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
```

Create a `ViewModel` class containing a collection of `Event` objects as well as a `Reorder` command implementation considering the `Events` will be grouped according to the `Day` property. Inside the `Reorder` command you will have access to some useful details through the `ReorderEndedCommandContext` such as:

<snippet id='listview-grouping-reorderitems-viewmodel' />

And the business model:

<snippet id='listview-grouping-reorderitems-businessobject'/>

The following image shows the result:

![ListView Reorder in grouped scenario](../images/listview_grouping_reorderitems.png)

## See Also

- [Grouping]({%slug listview-features-grouping%})
- [Commands]({%slug listview-features-commands %})
