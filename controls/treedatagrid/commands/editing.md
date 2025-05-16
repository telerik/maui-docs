---
title: Editing Commands
page_title: .NET MAUI TreeDataGrid Documentation - Editing Commands
description: Lear how to use the editing commands in TreeDataGrid for .NET MAUI.
position: 2
slug: treedatagrid-commands-editing
---

# .NET MAUI TreeDataGrid Editing Commands

The [.NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) control provides the following commands for editing the data inside the column:

* `BeginEdit`&mdash;Provides an entry point just before the editing begins.
* `CancelEdit`&mdash;Provides an entry point just before the editing is canceled.
* `CommitEdit`&mdash;Provides an entry point just before the editing is committed.

The execution parameter of the `Editing Commands` is of type `EditContext` that exposes the following properties:

* `CellInfo`&mdash;Gets the cell information associated with the operation.
* `TriggerAction`&mdash;Gets the `SourceTriggerAction` value that triggered the operation.
* `Parameter`&mdash;Gets an optional parameter holding additional information associated with the operation.

## BeginEdit and CommitEdit Commands Example

As the TreeDataGrid inherits from the DataGrid, for a runnable example with the Editing commands, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **DataGrid > Commands** category. 

## See Also

- [DataGrid Styling]({%slug treedatagrid-styling%})
- [Columns Styling]({%slug treedatagrid-columns-styling%})
