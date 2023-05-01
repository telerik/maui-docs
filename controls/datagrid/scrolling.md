---
title: Scrolling
page_title: .NET MAUI DataGrid Documentation - Scrolling
description: "Try now the Telerik UI for .NET MAUI DataGrid programmatic scrolling with the ScrollItemIntoView method."
position: 8
slug: datagrid-scrolling
tags: programmatic, scrolling
---

# .NET MAUI DataGrid Scrolling

The Telerik UI for .NET MAUI DataGrid has an internal scrolling mechanism achieved by the supported vertical and horizontal scrollbars for scrolling through its data.

>important Avoid nesting the DataGrid in a ScrollView and other controls that provide scrolling.

For implementing programmatic scrolling to a specific item, the DataGrid exposes the `ScrollItemIntoView(object item)` method, which brings the specified data item into view. Note that `ScrollItemIntoView` works in scenarios where the DataGrid Rows are with the same height. For more details, review the article on [setting the .NET MAUI DataGrid rows]({%slug datagrid-row-height%}).

The following example shows how to scroll to the last item of the DataGrid. The code executes on a button click.

```C#
private void Button_Clicked(object sender, System.EventArgs e)
{
    var item = this.vm.Clubs[this.vm.Clubs.Count - 1];
    this.grid.ScrollItemIntoView(item);
}
```

The following image shows the end result.

![DataGrid Programmatic Scrolling](images/datagrid-scrollintoview.gif)

## Additional Resources

- [.NET MAUI DataGrid Product Page](https://www.telerik.com/maui-ui/datagrid)
- [.NET MAUI DataGrid Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Setting the Telerik UI for .NET MAUI DataGrid Columns]({%slug datagrid-columns-overview%})
- [Grouping in the DataGrid]({%slug datagrid-grouping-overview%})
- [Aggregating Data in the DataGrid]({%slug datagrid-aggregates%})
- [Sorting .NET MAUI DataGrid Records]({%slug datagrid-sorting-overview%})
- [Filtering .NET MAUI DataGrid Records]({%slug datagrid-filtering-overview%})
