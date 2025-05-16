---
title: Row Details
page_title: .NET MAUI TreeDataGrid Documentation - Row Details
description: Learn how to present additional information about DataGrid rows by using the row details functionality.
position: 0
slug: treedatagrid-row-details
---

# .NET MAUI TreeDataGrid Row Details

The [Telerik UI for .NET MAUI TreeDataGrid]({%slug datagrid-overview%}) control is capable of presenting additional information through the Row Details functionality. The Row Details is a Data Template defined on the grid or row level and is used for displaying data without affecting the dimensions of the row and the cells within it.

To show the Row Details, you can use the following exposed options:

- The default `DataGridToggleRowDetailsColumn` column &mdash;Allows showing and hiding the row details for an item. For additional information, refer to the DataGrid [Toggle Row Details Column]({%slug datagrid-columns-toggle-column %})
- Using an additional element inside the TreeDataGrid Column `CellContentTemplate` and on its click, tap event, to show or hide the row details.

The DataGrid exposes the following properties that control the row details functionality:

* `AreRowDetailsFrozen` (type `bool`)&mdash;The property indicates whether the row details keep their position during horizontal scroll.

* `ExpandedRowDetails` (type `IList`)&mdash;Defines the collection of items that have expanded row details.

* `CanUserExpandMultipleRowDetails` (type `bool`)&mdash;The property indicates whether multiple row details can be expanded.

## Row Details Template

The [.NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) control inherits the `RowDetailsTemplate` property (type `DataTemplate`). The property is used for displaying row details. 

## See Also

- [.NET MAUI TreeDataGrid Product Page](https://www.telerik.com/maui-ui/treedatagrid)
- [.NET MAUI TreeDataGrid Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
