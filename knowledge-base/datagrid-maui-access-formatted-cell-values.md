---
title: Accessing Formatted DataGrid Cell Values in MAUI
description: Learn how to access and output the formatted string values of DataGrid cells in a MAUI application.
type: how-to
page_title: How to Access and Output Formatted DataGrid Cell Values in MAUI
slug: datagrid-maui-access-formatted-cell-values
tags: datagrid, maui, cell values, formatted strings, datagridcolumn, getvalueforinstance
res_type: kb
---

## Environment

| Product | Version |
| --- | --- |
| DataGrid for MAUI | 7.1.0 |

## Description

I need to access the result string in each cell for the DataGrid columns where MemberDataBinding is used, and format strings and converters are applied. I want to loop through the items and output exactly what the DataGrid is displaying.

This KB article also answers the following questions:
- How can I get the displayed value of a DataGrid cell in MAUI?
- What method should I use to extract formatted cell values from a DataGrid in MAUI?
- How to loop through DataGrid items and access their displayed values in MAUI?

## Solution

To access and output the formatted string values of DataGrid cells, use the `GetValueForInstance` method of the [DataGridColumn](https://docs.telerik.com/devtools/maui/controls/datagrid/columns/datagrid-columns-overview). This method returns the value of the `DataMemberBinding` by considering its converters and formats.

Here is an example demonstrating how to use the `GetValueForInstance` method:

```csharp
private void Grid_Loaded(object sender, System.EventArgs e)
{
    foreach (DataItem item in this.grid.GetDataView().Items)
    {
        foreach (var column in this.grid.Columns)
        {
            var cellValue = column.GetValueForInstance(item);
            // Output or use the cellValue as needed
        }
    }
}
```

In this example, `grid` refers to your DataGrid instance. Ensure you adjust `DataItem` to match the type of items in your DataGrid's data source.

## See Also

- [DataGrid Columns Overview in MAUI](https://docs.telerik.com/devtools/maui/controls/datagrid/columns/datagrid-columns-overview)
- [Data Binding in DataGrid for MAUI](https://docs.telerik.com/devtools/maui/controls/datagrid/data-binding)
