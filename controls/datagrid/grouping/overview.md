---
title: Overview
page_title: .NET MAUI DataGrid Documentation - Grouping Overview
description: "Review the Telerik .NET MAUI DataGrid Grouping documentation article to learn more about all built in Grouping functions you can use."
position: 0
slug: datagrid-grouping
---

# Overview

`Telerik UI for .NET MAUI DataGrid` provides a programmatic as well as a drag and drop approach for grouping its data based on a specific criteria

## Grouping UI

The DataGrid Grouping UI introduces the `DataGridGroupingPanel`, a new part of the DataGrid visual tree displayed at the top.

The `DataGridGroupingPanel` allows for a simple drag and drop grouping functionality.

> For more information about Grouping UI review the [Grouping UI]({%slug datagrid-grouping-ui%}) article of the DataGrid.

## Programmatic Grouping

Programmatic grouping can be done by adding descriptors to the `GroupDescriptors` collection. There are two types of descriptors:

* `PropertyGroupDescriptor`&mdash;Uses a property from the model as a group key.
* `DelegateGroupDescriptor`&mdash;Creates a custom group key which you can use.

## Expand and Collapse Groups

The `DataGrid` supports group expand and collapse operations either through the UI by tapping on the group headers, or programmatically. By default, all the groups are expanded.

## See Also

- [Grouping UI]({%slug datagrid-grouping-ui%})