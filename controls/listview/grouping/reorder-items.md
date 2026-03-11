---
title: Reorder Items in Grouped ListView
page_title: .NET MAUI ListView Documentation - Reorder Items in Grouped ListView
description: Check how to enable the Telerik UI for .NET MAUI ListView option for reordering when its items are grouped and how to programmatically update the dragged item details.
position: 4
slug: listview-grouping-reorderitems
previous_url: /controls/listview/grouping/listview-grouping-reorderitems
tags: group, radlistview, reordering
---

@[template](/_contentTemplates/common/listview-obsolete.md#listview-obsolete)

# .NET MAUI ListView Reorder Items in Grouped scenario

This help topic will provide an overview on how you can enable reordering feature of the ListView control when its items are grouped.

>tip Before proceeding, check the [Reorder Items]({%slug listview-features-reorder-items%}) topic which describes in details the reordering functionality of the ListView.

When the items of the ListView are grouped by certain criteria and the end user drags/starts reordering an item, the dragged item can be added to a different group. Since this depends on the items' relation, to handle the scenario, you need to subscribe to the ListView `Reorder` command and manually update the dragged item details.

The `ReorderEndedCommandContext` gives you access to the following properties:

* `Item`&mdash;Refers to the data item that is being interacted with.
* `DestinationItem`&mdash;Refers to the data item that corresponds to the location where the dragged item has been released.
* `Group`&mdash;Gets the group containing the data item that is being interacted with.
* `DestinationGroup`&mdash;Refers to the group that corresponds to the location where the dragged item has been released.
* `Placement` (of type `ItemReorderPlacement`)&mdash;Indicates whether the dragged item have to be placed before or after the destination item.

## See Also

- [Grouping]({%slug listview-features-grouping%})
- [Commands]({%slug listview-features-commands %})
