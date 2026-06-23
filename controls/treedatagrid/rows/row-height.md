---
title: Row Height
page_title: .NET MAUI TreeDataGrid Documentation - Row Height
description: Learn how to set row height and customize text positioning, margins, and alignment in the .NET MAUI TreeDataGrid.
position: 3
slug: treedatagrid-row-height
---

# .NET MAUI TreeDataGrid Row Height

The [Telerik UI for .NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) provides full control over the way the content is accommodated inside the DataGrid by enabling you to manually set the height of its rows.

By default, the row height is calculated according to the cell content.

To set the row height, apply the `RowHeight` property of type `double` to the TreeDataGrid instance.

```XAML
<telerik:RadTreeDataGrid x:Name="treeDataGrid"
						 RowHeight="50"
						 ItemsSource="{Binding Source}" />
```

## See Also

- [Setting the Telerik UI for .NET MAUI TreeDataGrid Columns]({%slug treedatagrid-columns-overview%})
- [Sorting .NET MAUI TreeDataGrid Records]({%slug treedatagrid-sorting%})
- [Filtering .NET MAUI TreeDataGrid Records]({%slug treedatagrid-filtering-overview%})


