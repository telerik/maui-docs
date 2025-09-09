---
title: Expand and Collapse Items
page_title: .NET MAUI TreeDataGrid Documentation - Expand Collapse Items
description: Learn about the Telerik UI for .NET MAUI TreeDataGrid methods and how to expand or collapse a parent node programatically.
position: 20
tags: methods
slug: treedatagrid-methods
---

# Expand and Collapse Items in .NET MAUI TreeDataGrid

The [Telerik UI for .NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) lets you expand and collapse item either through the UI—by tapping on the expand/collapse icon or programmatically.

The TreeDataGrid allows you to collapse all items by setting the `AutoExpandGroups` (`bool`) property. The default value is `false`, which means, all items are expanded.

## Expand and Collapse Specific Items

The TreeDataGrid exposes the following methods to expand and collapse the children of an item:

* `Expand`(`object item`)&mdash;Expands the children of the item.
* `Collapse`(`object item`)&mdash;Collapses the children of the item.

Use the `IsExpanded` (`object item`) method to get a value whether the item is currently expanded (has its children visible). Returns `true` if the item is expanded, otherwise `false`.

## Additional Resources

- [.NET MAUI TreeDataGrid Product Page](https://www.telerik.com/maui-ui/treedatagrid)
- [.NET MAUI TreeDataGrid Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Setting the .NET MAUI TreeDataGrid Columns]({%slug treedatagrid-columns-overview%})