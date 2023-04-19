---
title: Rows
page_title: .NET MAUI DataGrid Documentation - Row Height
description:
position: 10
slug: datagrid-row-height
---

# .NET MAUI DataGrid Row Height

The Telerik UI for .NET MAUI DataGrid provides the option to manually set the grid row height, so you have full control over the way the content is accommodated inside the grid cells.  By default row height is calculated according to the cells content.

Apply `RowHeight` property of type `double` to the DataGrid instance to specify the row height:


```XAML
<telerik:RadDataGrid x:Name="dataGrid"
							RowHeight="50"
							ItemsSource="{Binding Source}" />
```

Here is the difference in the way DataGrid is rendered with and without `RowHeight` specifically set:

![.NET MAUI DataGrid RowHeight](images/datagrid-row-height.png)

>Take a look at the [CellContentStyle]({%slug datagrid-columns-styling%}#cellcontentstyle) topic for additional customization options related to positioning the text inside the cells, such as text margin and text alignment as this can also affect the overall row height.


## Additional Resources

- [Setting the Telerik UI for .NET MAUI DataGrid Columns]({%slug datagrid-columns-overview%})
- [Aggregating Data in the DataGrid]({%slug datagrid-aggregates%})
- [Sorting .NET MAUI DataGrid Records]({%slug datagrid-sorting-overview%})
- [Filtering .NET MAUI DataGrid Records]({%slug datagrid-filtering-overview%})

## See Also

- [.NET MAUI DataGrid Product Page](https://www.telerik.com/maui-ui/datagrid)
- [.NET MAUI DataGrid Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
