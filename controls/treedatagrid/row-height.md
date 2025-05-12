---
title: Rows
page_title: .NET MAUI TreeDataGrid Documentation - Row Height
description: Learn more how to set the row height and apply custom settings for positioning the text, setting the text margins, and defining the text alignment when working with the Telerik UI for .NET MAUI TreeDataGrid.
position: 3
slug: treedatagrid-row-height
---

# .NET MAUI TreeDataGrid Row Height

The [Telerik UI for .NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) provides full control over the way the content is accommodated inside the DataGrid by enabling you to manually set the height of its rows.

By default, the row height is calculated according to the cell content.

For more information on customizing the row style, positioning the text inside the cells, setting the text margins, and defining the text alignment, see the topic about [customizing the content style of the .NET MAUI TreeDataGrid cell]({%slug treedatagrid-columns-styling%}#cellcontentstyle).

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


