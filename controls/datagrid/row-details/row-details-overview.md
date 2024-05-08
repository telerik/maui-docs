---
title: Overview
page_title: .NET MAUI DataGrid Documentation - Row Details Overview
description: Learn how to present additional information about DataGrid rows by using the row details functionality.
position: 0
slug: datagrid-row-details-overview
---

# .NET MAUI DataGrid Row Details Overview

The [Telerik UI for .NET MAUI DataGrid]({%slug datagrid-overview%}) control is capable of presenting additional information through the Row Details functionality. The Row Details is a Data Template defined on the grid or row level and is used for displaying data without affecting the dimensions of the row and the cells within it.

![DataGrid Row Details Overview](images/datagrid-row-details.png)

To show the Row Details, you can use the following exposed options:

- The default `DataGridToggleRowDetailsColumn` column &mdash;Allows showing and hiding the row details for an item. For additional information, refer to the DataGrid [Toggle Row Details Column]({%slug datagrid-columns-toggle-column %})

- For example, on a selection without using the default column. For this case you need a custom implementation. 

Here is a sample implementation inside the DataGrid `SelectionChanged` event:

```C#
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

The DataGrid exposes the following properties that control the row details functionality:

* `AreRowDetailsFrozen` (type `bool`)&mdash;The property indicates whether the row details keep their position during horizontal scroll.

* `ExpandedRowDetails` (type `IList`)&mdash;Defines the collection of items that have expanded row details.

* `CanUserExpandMultipleRowDetails` (type `bool`)&mdash;The property indicates whether multiple row details can be expanded.


>tip For an outline of all DataGrid features review the [.NET MAUI DataGrid Overview]({%slug datagrid-overview%}) article.

## Next Steps

- [Row Details Template]({%slug datagrid-row-details-template %})

## See Also

- [.NET MAUI DataGrid Product Page](https://www.telerik.com/maui-ui/datagrid)
- [.NET MAUI DataGrid Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
