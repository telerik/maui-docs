---
title: DataGrid
meta_title: .NET MAUI RefreshView Documentation - Integration with DataGrid
description: Learn how to add pull-to-refresh to the Telerik UI for .NET MAUI DataGrid by wrapping it in the RefreshView and binding a refresh command.
components: ["refreshview"]
tags: .net maui, telerik .net maui, ui for .net maui, refreshview, datagrid, microsoft .net maui
position: 1
slug: refreshview-datagrid
---

# .NET MAUI RefreshView Integration with DataGrid

You can add pull-to-refresh to the [Telerik UI for .NET MAUI DataGrid]({% slug datagrid-overview %}) by wrapping the DataGrid in the RefreshView. Use this approach to let users reload tabular data, for example, orders or customer records from a server, by pulling the grid.

![.NET MAUI RefreshView wrapping a DataGrid with customer columns and a refresh indicator shown above the column headers](../images/refreshview-integration-datagrid.png)

## How the Integration Works

Wrap the `RadDataGrid` in the `RadRefreshView` as its content. When the user pulls the grid past the pulling threshold and releases it, the RefreshView starts a refresh and executes its `Command`.

To connect the RefreshView to your view model, bind the following properties:

* `Command` (`ICommand`)&mdash;Executes the view model logic that reloads the rows.
* `IsRefreshing` (`bool`)&mdash;Reflects whether a refresh is in progress. The view model sets the property to `false` when the rows are loaded to end the refresh.

For more information about the command properties, see [RefreshView Commands]({% slug refreshview-commands %}).

## Refresh the DataGrid Rows

The following example demonstrates how to use the RefreshView with the DataGrid.

1. Define the RefreshView and the DataGrid in XAML:

    <snippet id='refreshview-integration-datagrid' />

2. Add the `telerik` namespace:

    ```XAML
    xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
    ```

3. Define the `ViewModel` with the items, the `IsRefreshing` property, and the `RefreshCommand`:

    <snippet id='refreshview-integration-viewmodel' />

4. Define the `Customer` business object:

    <snippet id='refreshview-integration-customer' />

> tip For a runnable example with the RefreshView Integration with DataGrid scenario, see the [SDKBrowser Demo Application]({% slug sdkbrowser-app %}) and go to the **RefreshView > Integration** category.

## See Also

- [RefreshView Integration with CollectionView]({% slug refreshview-collectionview %})
- [RefreshView Commands]({% slug refreshview-commands %})
- [Refresh State]({% slug refreshview-refresh-state %})
- [DataGrid Overview]({% slug datagrid-overview %})
