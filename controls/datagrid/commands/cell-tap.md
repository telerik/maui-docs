---
title: CellTap Command
page_title: .NET MAUI DataGrid Documentation - CellTap Command
description: Check our &quot;CellTap Command&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 1
slug: datagrid-commands-cell-tap
---

# .NET MAUI DataGrid CellTap Command

The DataGrid `CellTap` command handles the tap (click) gesture over a grid cell, that is, the intersection of a data row and a column.

## Example

Here is an example how the [.NET MAUI DataGrid]({%slug datagrid-overview%}) `CellTap` command works:

**1.** Create the needed business objects, for example, type `Country` with the following properties:

<snippet id='datagrid-commands-celltap-businessobject'/>

**2.** Add data to the `DataGrid` `ItemsSource` and set the `BindingContext`:

<snippet id='datagrid-commands-celltap-data'/>

**3.** Handle the `CellTap` action as a command. First, create a class that inherits from the `DataGridCommand` and set its `Id` property. You will also need to override the `CanExecute` and `Execute` methods as demonstrated in the example below:

<snippet id='datagrid-commands-celltap'/>

**4.** Add this command to the `Commands` collection of the `RadDataGrid` instance:

<snippet id='datagrid-commands-cetttap-add'/>

**5.** Define the DataGrid in XAML:

<snippet id='datagrid-commands-celltap-xaml'/>

**6.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## See Also

- [Editing]({%slug datagrid-commands-editing%})
- [Validation]({%slug datagrid-commands-validation%})
