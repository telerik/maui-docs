---
title: Detecting Row Detail Expansion or Collapse in DataGrid for MAUI
description: Learn how to identify when a row detail in the DataGrid for .NET MAUI is expanded or collapsed using MVVM.
type: how-to
page_title: How to Detect Row Detail Expansion or Collapse in .NET MAUI DataGrid
slug: detect-row-detail-expansion-collapse-maui-datagrid
tags: datagrid, rowdetails, expandedrowdetails, toggle, mvvm, maui
res_type: kb
---

## Environment

| Product | Version |
| --- | --- |
| DataGrid for .NET MAUI | 7.0.0 |

## Description

In a MAUI application using the DataGrid, I need to detect when a row detail is expanded or collapsed while following the MVVM pattern.

This KB article also answers the following questions:
- How can I listen to row detail state changes in a DataGrid?
- Is there a way to bind the expansion state of row details in DataGrid to a ViewModel?
- Can I use MVVM to track the expansion and collapse of row details in DataGrid?

## Solution

To detect when a row detail is expanded or collapsed in the [DataGrid](https://docs.telerik.com/devtools/maui/controls/datagrid/commands/overview) for MAUI using MVVM, you can employ one of the following approaches:

### Approach 1: Using the `ExpandedRowDetails` Collection

1. Bind the `ExpandedRowDetails` property of the DataGrid to an observable collection in the ViewModel. This collection holds the items for which the row details are currently expanded.

2. Monitor the `CollectionChanged` event of the observable collection. Additions to the collection indicate row detail expansions, while removals indicate collapses. Implement the required logic within the event handler to respond to these changes.

### Approach 2: Using the `ToggleRowDetailsButtonTap` Command

1. Utilize the `ToggleRowDetailsButtonTap` command provided by the DataGrid. This command is triggered whenever the toggle button for row details is tapped.

2. In the command's execution logic, add a flag or a mechanism to check whether the item related to the toggled row detail is present in the `ExpandedRowDetails` collection. An item's presence indicates an expansion, while its absence indicates a collapse.

 Implement the necessary logic based on this condition to handle the expansion or collapse state.

Both approaches allow for handling row detail expansion and collapse states in a MVVM-compliant manner, enabling you to perform actions or update the UI accordingly.

## See Also

- [DataGrid Commands Overview](https://docs.telerik.com/devtools/maui/controls/datagrid/commands/overview)
- [DataGrid Row Details Documentation](https://docs.telerik.com/devtools/maui/controls/datagrid/rowdetails)
