---
title: Managing Row Details in DataGrid for MAUI on Cell or Row Selection
description: Learn how to toggle row details in a DataGrid for MAUI application based on cell or row selection.
type: how-to
page_title: How to Display Row Details Based on Cell or Row Selection in DataGrid for MAUI
slug: datagrid-maui-toggle-row-details-cell-selection
tags: datagrid, maui, row details, cell selection, row selection, expandedrowdetails, selectionchanged
res_type: kb
---

## Environment

| Product | Version | Author |
| --- | --- | --- |
| DataGrid for .NET MAUI | 7.1.0 | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

In a DataGrid for MAUI, I want to show or hide row details based on cell selection without using the default `DataGridToggleRowDetailsColumn`. The goal is to use the `SelectionChanged` event to achieve this functionality. This KB article also answers the following questions:
- How can I show row details on cell selection in a DataGrid?
- What is the method to toggle row details visibility based on cell selection?
- How to use the `SelectionChanged` event to show row details in the DataGrid for MAUI?

## Solution

To display row details based on cell selection, you must first define a `RowDetailsTemplate`. For more information on how to set up a `RowDetailsTemplate`, refer to the [official documentation]({%slug datagrid-row-details-template%}).

### Handling Cell Selection

When the `SelectionUnit` is set to `Cell`, the item within the `e.AddedItems` or `e.RemovedItems` collections is of type `DataGridCellInfo`. To add or remove items from the `ExpandedRowDetails` collection based on cell selection, use the following approach:

```csharp
void dataGrid_SelectionChanged(System.Object sender, DataGridSelectionChangedEventArgs e)
{
    RadDataGrid dataGrid = sender as RadDataGrid;

    foreach (DataGridCellInfo item in e.AddedItems)
    {
        dataGrid.ExpandedRowDetails.Add(item.Item);
    }
    foreach (DataGridCellInfo item in e.RemovedItems)
    {
        dataGrid.ExpandedRowDetails.Remove(item.Item);
    }
}
```

This code listens for the `SelectionChanged` event and appropriately adds or removes the items associated with the selected or deselected cells to or from the `ExpandedRowDetails` collection, thus showing or hiding the row details.

### Handling Row Selection

If the `SelectionUnit` is set to `Row`, the objects in the `e.AddedItems` and `e.RemovedItems` collections are your business objects. You can handle them as follows:

```csharp
void dataGrid_SelectionChanged(System.Object sender, DataGridSelectionChangedEventArgs e)
{
    RadDataGrid dataGrid = sender as RadDataGrid;

    foreach (var item in e.AddedItems)
    {
        dataGrid.ExpandedRowDetails.Add(item);
    }
    foreach (var item in e.RemovedItems)
    {
        dataGrid.ExpandedRowDetails.Remove(item);
    }
}
```

This snippet functions similarly to the cell selection scenario but is tailored for when entire rows are selected.

## Notes

- Ensure the `SelectionUnit` property of the `RadDataGrid` is properly set according to your requirements (`Cell` or `Row`).
- The `ExpandedRowDetails` collection directly controls the visibility of row details.
