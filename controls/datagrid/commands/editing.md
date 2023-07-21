---
title: Editing Commands
page_title: .NET MAUI DataGrid Documentation - Editing Commands
description: Check our &quot;Editing Commands&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 2
slug: datagrid-commands-editing
---

# .NET MAUI DataGrid Editing Commands

The DataGrid control provides the following commands for editing the data inside the column:

* `BeginEdit`&mdash;Provides an entry point just before the editing begins.
* `CancelEdit`&mdash;Provides an entry point just before the editing is canceled.
* `CommitEdit`&mdash;Provides an entry point just before the editing is committed.

The execution parameter of the `Editing Commands` is of type `EditContext` that exposes the following properties:

* `CellInfo`&mdash;Gets the cell information associated with the operation.
* `TriggerAction`&mdash;Gets the `SourceTriggerAction` value that triggered the operation.
* `Parameter`&mdash;Gets an optional parameter holding additional information associated with the operation.

## BeginEdit and CommitEdit Commands Example

Here is an example how the DataGrid `Editing` commands work.

1. Create the needed business objects, for example type `Data` with the following properties:

 <snippet id='datagrid-commands-editing-businessobject'/>

1. Chen, create a `ViewModel` with a collection of Data objects:

 <snippet id='datagrid-commands-editing-viewmodel'/>

1. Set the `ViewModel` class as `BindingContext` of the page:

 ```C#
this.BindingContext = new ViewModel();
 ```

1. Handle the `BeginEdit` action as a `Command`. First, create a class that inherits from the `DataGridCommand` and set its `Id` property. You will also need to override the `CanExecute` and `Execute` methods as demonstrated in the example below:

 <snippet id='datagrid-commands-editing-beginedit'/>

1. Handle the `CommitEdit` action as a `Command`. First, create a class that inherits from the `DataGridCommand` and set its `Id` property. You will also need to override the `CanExecute` and `Execute` methods as demonstrated in the example below:

 <snippet id='datagrid-commands-editing-commitedit'/>

1. Add this `Command` to the `Commands` collection of the `RadDataGrid` instance:

 <snippet id='datagrid-commands-editing-binding'/>

1. Define the DataGrid in XAML:

 <snippet id='datagrid-commands-editing'/>

## See Also

- [Validation]({%slug datagrid-commands-validation%})
- [DataGrid Styling]({%slug datagrid-styling%})
- [Columns Styling]({%slug datagrid-columns-styling%})
