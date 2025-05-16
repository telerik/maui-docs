---
title: Scrolling
page_title: .NET MAUI TreeDataGrid Documentation - Scrolling
description: "Try now the Telerik UI for .NET MAUI TreeDataGrid programmatic scrolling with the ScrollItemIntoView method."
position: 8
slug: treedatagrid-scrolling
tags: programmatic, scrolling
---

# .NET MAUI TreeDataGrid Scrolling

The [Telerik UI for .NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) has an internal scrolling mechanism achieved by the supported vertical and horizontal scrollbars for scrolling through its data.

>important Avoid nesting the TreeDataGrid in a `ScrollView` and other controls that provide scrolling.

For the implementation of programmatic scrolling to a specific item, use the `ScrollItemIntoView(object item)` method, which brings the specified data item into view. Note that `ScrollItemIntoView` works in scenarios where the TreeDataGrid Rows are with the same height.

For more details, review the article on [setting the .NET MAUI TreeDataGrid rows]({%slug treedatagrid-row-height%}).

## See Also

- [Setting the Telerik UI for .NET MAUI TreeDataGrid Columns]({%slug treedatagrid-columns-overview%})
- [Sorting .NET MAUI TreeDataGrid Records]({%slug treedatagrid-sorting%})
- [Filtering .NET MAUI TreeDataGrid Records]({%slug treedatagrid-filtering-overview%})
