---
title: Rows
page_title: .NET MAUI DataGrid Documentation - Row Height
description: "Learn more how to set the row height and apply custom settings for positioning the text, setting the text margins, and defining the text alignment when working with the Telerik UI for .NET MAUI DataGrid."
position: 10
slug: datagrid-row-height
---

# .NET MAUI DataGrid Row Height

The Telerik UI for .NET MAUI DataGrid provides full control over the way the content is accommodated inside the DataGrid by enabling you to manually set the height of its rows.

By default, the row height is calculated according to the cell content.

For more information on customizing the row style, positioning the text inside the cells, setting the text margins, and defining the text alignment, see the topic about [customizing the content style of the .NET MAUI DataGrid cell]({%slug datagrid-columns-styling%}#cellcontentstyle).

To set the row height, apply the `RowHeight` property of type `double` to the DataGrid instance.

```XAML
<telerik:RadDataGrid x:Name="dataGrid"
							RowHeight="50"
							ItemsSource="{Binding Source}" />
```

The following image shows the difference in the way the DataGrid is rendered with and without `RowHeight` specifically set:

![.NET MAUI DataGrid RowHeight](images/datagrid-row-height.png)

## Additional Resources

- [.NET MAUI DataGrid Product Page](https://www.telerik.com/maui-ui/datagrid)
- [.NET MAUI DataGrid Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Setting the Telerik UI for .NET MAUI DataGrid Columns]({%slug datagrid-columns-overview%})
- [Aggregating Data in the DataGrid]({%slug datagrid-aggregates%})
- [Sorting .NET MAUI DataGrid Records]({%slug datagrid-sorting-overview%})
- [Filtering .NET MAUI DataGrid Records]({%slug datagrid-filtering-overview%})


