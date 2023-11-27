---
title: Overview
page_title: .NET MAUI DataGrid Documentation - Overview
description: Check our &quot;Overview&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 0
previous_url: /controls/datagrid/commands/commands
slug: datagrid-commands-overview
---

# .NET MAUI DataGrid Commands

The command design-pattern is very important and widely used in the XAML and MVVM world. The DataGrid strictly follows these best practices and provides an intuitive and an easy-to-use set of APIs that allow different aspects of the DataGrid behavior to be handled and/or completely overridden.

The DataGrid exposes a `Commands` collection that allows you to register custom commands with each control instance through the `RadDataGrid.Commands` property:

* `Commands`&mdash;Gets the collection with all the custom commands registered with the `CommandService`. Custom commands have higher priority than the built-in (default) ones.

## Command Types

* `DataGridCommand`&mdash;All the default commands within `RadDataGrid` derive from the base `DataGridCommand`. Think of this command as a UI-related command as it operates over the `RadDataGrid` instance that owns the command.

 * `Id`&mdash;The key that relates a command instance to a particular action/routine. This value is used to associate a command with a known event within a `RadDataGrid` instance.
 * `Command`&mdash;Gets or sets the generic `ICommand` implementation that may come from the `ViewModel`.
 * `EnableDefaultCommand`&mdash;Gets or sets a value indicating whether the default (built-in) UI command associated with the specified `Id` will be executed. The default value is `True`.      

## DataGridCommandId Enumeration

All the predefined commands within a `RadDataGrid` instance are identified by a member of the `DataGridCommandId` enumeration. This is actually the key that relates a command instance to a particular action/routine within the owning grid. To register a custom command within a `RadDataGrid` instance, you can inherit the `DataGridCommand` class and override its `CanExecute` and `Execute` methods. You need to set the `Id` property of the new command so that it can be properly associated with the desired action/event. Following are the members of the `DataGridCommandId` enumerations.

The table below shows all commands in the DataGrid control and for each of the available commands there is an object which is passed as a `parameter` in its `Execute` method.

| Commands | Object type |
| -------- | ---------- |
| Unknown | `DataGridColumn` |
| `ColumnHeaderTap`  | `DataGridTextColumn` |
| `GroupHeaderTap`      | `GroupHeaderContext` |
| `GroupHeaderButtonTap`      | `GroupHeaderContext` |
| `CellTap` | `DataGridCellInfo` |
| `CellDoubleTap` | `DataGridCellInfo` |
| `GenerateColumn` | `GenerateColumnContext` |
| `DataBindingComplete` | `DataBindingCompleteEventArgs` |
| `BeginEdit` | `EditContext` |
| `CancelEdit` | `EditContext` |
| `CommitEdit` | `EditContext` |
| `ValidateCell` | `ValidateCellContext` |
| `LoadMoreData` | `LoadOnDemandContext` |
| `FilterTap` | `FilterTapContext` |
| `ApplyFilter` | `FilterTapContext` |
| `CloseFilter` | `FilterTapContext` |
| `ResetFilter` | `FilterTapContext` |
| `KeyDown` | `KeyboardInfo` |
| `ToggleRowDetailsButtonTap` | the `type` is the data model |

>tip For an outline of all DataGrid features review the [.NET MAUI DataGrid Overview]({%slug datagrid-overview%}) article.

## See Also

- [CellTap Command]({%slug datagrid-commands-cell-tap%})
- [Editing Command]({%slug datagrid-commands-editing%})
- [Validation Command]({%slug datagrid-commands-validation%})
