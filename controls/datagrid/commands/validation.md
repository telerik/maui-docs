---
title: Validation Command
page_title: .NET MAUI DataGrid Documentation - Validation Command
description: Check our &quot;Validation Command&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 3
slug: datagrid-commands-validation
---

# Validation Command

The DataGrid control provides a validation command that has an entry point for validating cells content. The execution parameter is of type `ValidateCellContext` and exposes the following properties:

* `CellInfo`&mdash;Gets the cell information associated with the operation.
* `Errors`&mdash;Gets or sets the errors (if any) that occurred during the validation.

## Example

Here is an example how the DataGrid `ValidateCell` command works:

1. Create a `Data` class (the business object) that inherits from the `INotifyDataErrorInfo` and `INotifyPropertyChanged` interfaces. For demonstration purposes, the example will do the validation through the `INotifyDataErrorInfo` interface.

 <snippet id='datagrid-commands-validation-businessobject'/>

T1. Create a `ViewModel` with a collection of `Data` objects:

 <snippet id='datagrid-commands-validation-viewmodel'/>

1. Handle the `CellTap` action as a `Command`. First, create a class that inherits from the `DataGridCommand` and set its `Id` property accordingly. You will also need to override the `CanExecute` and `Execute` methods as demonstrated in the example below:

 <snippet id='datagrid-commands-validation-validatecell'/>

1. Set the `BindingContext` to be the `ViewModel` and add this command to the `Commands` collection of the `RadDataGrid` instance:

 <snippet id='datagrid-commands-validation-binding'/>

1. Define the DataGrid in XAML:

  <snippet id='datagrid-commands-validation'/>


 1. Use the `telerik` namespace:

  ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

## See Also

- [CellTap Command]({%slug datagrid-commands-cell-tap%})
- [Editing Command]({%slug datagrid-commands-editing%})
- [Columns Styling]({%slug datagrid-columns-styling%})
