---
title: Getting Column and Row Index Using Cell Tap Command in DataGrid for MAUI
description: Learn how to retrieve the column index and row index when using the Cell Tap command in the DataGrid for MAUI.
type: how-to
page_title: Retrieve Column and Row Index with Cell Tap Command in MAUI DataGrid
meta_title: Retrieve Column and Row Index with Cell Tap Command in MAUI DataGrid
slug: retrieve-column-row-index-cell-tap-maui-datagrid
tags: datagrid,maui,column,row,index,cell-tap
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.1 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to retrieve the column index and row index by using the Cell Tap command in the [DataGrid for MAUI]({%slug datagrid-overview%}).

This knowledge base article also answers the following questions:
- How to determine tapped cell row and column index in MAUI DataGrid?
- How to use `DataGridCellInfo` to get row and column index in MAUI DataGrid?
- How to implement a custom `CellTap` command for MAUI DataGrid?

## Solution

To achieve this, use the `GetDataView` method of the DataGrid to access the sorted, filtered, and grouped view of the items. The `DataGridCellInfo` parameter provides information about the tapped cell's value, column, and row item. Combine these approaches to calculate the row index.

Follow these steps:

1. Implement a custom `DataGridCommand` to handle the Cell Tap event.
2. Access the `DataGridCellInfo` parameter to retrieve the value, column, and row item.
3. Use the `GetDataView` method to get the DataGrid's view of the data.
4. Retrieve the row index using the `IndexOf` method.
5. Optionally, you can display a message or take further actions based on this data.

Here's an example implementation:

```csharp
public class CellTapUserCommand : DataGridCommand
{
    public CellTapUserCommand()
    {
        Id = DataGridCommandId.CellTap;
    }

    public override bool CanExecute(object parameter)
    {
        return true;
    }

    public override void Execute(object parameter)
    {
        if (parameter is not DataGridCellInfo context)
            return;

        var cellValue = context.Value; // The value of the tapped cell
        var cellColumn = context.Column; // The column of the tapped cell
        var rowValue = context.Item; // The row item

        // Get the DataView of the DataGrid
        var dv = cellColumn.DataGrid.GetDataView();

        int rowIndex = 0;
        if (dv.Items is IList list)
        {
            rowIndex = list.IndexOf(context.Item); // Get the row index
        }
        else
        {
            // Fallback: handle grouping or convert to list
            var itemsList = dv.Items.ToList();
            rowIndex = itemsList.IndexOf(rowValue);
        }

        var message = $"You tapped on {cellValue} inside {cellColumn.HeaderText} column, which is row index {rowIndex}!";

        Debug.WriteLine(message);

        // Optionally display a message
        App.Current?.MainPage?.DisplayAlert("CellTap Command:", message, "OK");

        // Execute the default command behavior
        this.Owner.CommandService.ExecuteDefaultCommand(DataGridCommandId.CellTap, parameter);
    }
}
```

## See Also

- [DataGrid Overview for MAUI](https://docs.telerik.com/devtools/maui/controls/datagrid/overview)
- [DataGrid Commands for MAUI](https://docs.telerik.com/devtools/maui/controls/datagrid/commands/overview)
