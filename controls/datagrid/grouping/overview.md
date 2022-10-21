---
title: Overview
page_title: .NET MAUI DataGrid Documentation - Grouping Overview
description: "Review the Telerik .NET MAUI DataGrid Grouping documentation article to learn more about all built in Grouping functions you can use."
position: 0
slug: datagrid-grouping-overview
---

# Overview

**Telerik UI for .NET MAUI DataGrid** supports grouping operations either through the UI - using the Grouping UI or programmatically through Property and Delegate group descriptors.

## Grouping UI

![Grouping UI](../images/grouping-ui-windows.gif)

The DataGrid Grouping UI is enabled by design on desktop and disabled on mobile, it allows the user to group the DataGrid by dragging and dropping the column headers to the `DataGridGroupingPanel`. 

The UI is represented by the `DataGridGroupingPanel`. The panel is part of the DataGrid and it is visualized at the top.

> For more information about Grouping UI review the [Grouping UI]({%slug datagrid-grouping-ui%}) article of the DataGrid.

## Programmatic Grouping

Programmatic grouping can be done by adding descriptors to the `GroupDescriptors` collection. There are two types of descriptors:

* `PropertyGroupDescriptor`&mdash;Uses a property from the model as a group key.
* `DelegateGroupDescriptor`&mdash;Creates a custom group key which you can use.

## Expand and Collapse Groups

The `DataGrid` supports group expand and collapse operations either through the UI by tapping on the group headers, or programmatically. By default, all the groups are expanded.

## See Also

- [Grouping UI]({%slug datagrid-grouping-ui%})
- [Property Group Descriptor]({%slug datagrid-property-group-descriptor%})
- [Delegate Group Descriptor]({%slug datagrid-delegate-group-descriptor%})