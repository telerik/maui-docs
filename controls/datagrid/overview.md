---
title: Overview
page_title: .NET MAUI DataGrid Overview - Telerik UI
description: Learn what the Telerik UI for .NET MAUI DataGrid can do, from columns and editing to sorting, paging, theming, and localization.
position: 0
tags: grid, data grid, maui grid, dot net maui grid, dotnet maui grid
previous_url: /controls/datagrid/datagrid-overview
slug: datagrid-overview
---

# .NET MAUI DataGrid Overview

The Telerik UI for [.NET MAUI DataGrid](https://www.telerik.com/maui-ui/datagrid) displays, edits, and organizes tabular data in .NET MAUI applications. Use it when you need a flexible grid that can handle large data sets, support common data operations, and adapt to desktop and mobile layouts.

The DataGrid uses rows, columns, and cells to represent business data in a familiar layout. It also uses UI virtualization so that row and cell visuals are created only when they are needed, which helps keep scrolling and interaction responsive.

Use the .NET MAUI DataGrid to:

* Display data from collections of business objects or `ViewModel` instances.
* Configure columns for different data types and editing scenarios.
* Let users sort, filter, group, search, and page through data.
* Improve usability with selection, row details, aggregates, and keyboard navigation.
* Customize styling, localization, empty states, and command handling.

The following image shows the DataGrid running on supported desktop and mobile platforms:

![The Telerik .NET MAUI DataGrid displaying tabular data on Android, iOS, macOS, and Windows.](images/datagrid-overview.png "Telerik .NET MAUI DataGrid on all platforms")

## MAUI DataGrid Video Tutorial

If you prefer a guided walkthrough, watch the MAUI DataGrid video tutorial. It covers the following topics:

* Introduction to Telerik MAUI DataGrid and its features.
* Set up the DataGrid in a .NET MAUI app.
* Configure the columns and use custom templates.
* Use sorting, filtering, and selection features.

<iframe width="560" height="315" src="https://www.youtube.com/embed/XxUvA4fKHzU" title="Take your .NET MAUI skills to the next level with Chapter 4 of the Telerik UI for .NET MAUI course! This video provides a comprehensive guide to .NET MAUI Grid control. Learn about its features, setup process, column configuration, and creating custom column templates. Discover how to enable sorting, filtering, and selection for a dynamic and powerful data presentation in your apps. Watch now and become a DataGrid expert!" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Key Features

The .NET MAUI DataGrid includes the following key features:

- Flexible columns and layout: Use the [built-in DataGrid column types]({%slug datagrid-columns-overview%}) such as Text, Boolean, Numeric, ComboBox, Date, Time, and Template to match your data. You can also enable [column reordering]({% slug datagrid-columns-reordering %}), [column resizing]({% slug datagrid-column-resizing %}), [frozen columns]({% slug datagrid-frozen-columns %}), [row height]({%slug datagrid-row-height%}) settings, and [column footer cells]({%slug datagrid-column-footer%}) to refine the layout.
- Built-in data operations: Apply [sorting]({%slug datagrid-sorting-overview %}), [filtering]({%slug datagrid-filtering-overview%}), and [grouping]({%slug datagrid-grouping-overview %}) per column, and enable [search as you type]({%slug datagrid-search-as-you-type%}) so users can quickly locate matching values in the `ItemsSource`.
- Editing and selection: Enable [DataGrid editing]({%slug datagrid-editing%}) so users can update values directly in the grid with editors that match the current column type. Use [single or multiple selection]({%slug datagrid-selection-overview%}) to support cell-based and row-based selection scenarios.
- Rich data presentation: Use [row details]({%slug datagrid-row-details-overview%}) to reveal additional information for a record without leaving the current view. Add [aggregate functions]({%slug datagrid-aggregates%}) such as `Sum`, `Count`, `Min`, `Max`, and `Average`, or implement a custom aggregate when needed.
- Performance for large data sets: Use [load on demand]({%slug datagrid-features-loadondemand%}) to request more records after the grid is displayed, and combine the grid with the Telerik UI for .NET MAUI [DataPager]({%slug datapager-overview%}) to [page data in the grid]({%slug datagrid-paging%}). When no records are available, show an [empty template]({%slug datagrid-empty-template%}) to explain the current state.
- Customization and localization: Add [DataGrid commands]({%slug datagrid-commands-overview %}) for custom interaction logic, enable keyboard navigation on WinUI and MacCatalyst, apply a [theme]({%slug themes-overview%}) or the [DataGrid styling API]({%slug datagrid-styling%}), and use [localization support]({%slug globalization-localization%}#localization) for built-in UI text.

## Next Steps

Continue with these articles to start using and refining the DataGrid:

- [Getting Started with Telerik UI for .NET MAUI DataGrid]({% slug datagrid-getting-started %})
- [Configure DataGrid column types and templates]({%slug datagrid-columns-overview%})
- [Customize the DataGrid appearance with styling]({%slug datagrid-styling%})

## See Also

- [.NET MAUI DataGrid Product Page](https://www.telerik.com/maui-ui/datagrid)
- [.NET MAUI DataGrid Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

<VideoMetadata 
    name="Mastering the DataGrid in Telerik UI for .NET MAUI: Setup, Columns, Sorting, and More | Chapter 4"
    description="Take your .NET MAUI skills to the next level with Chapter 4 of the Telerik UI for .NET MAUI course! This video provides a comprehensive guide to .NET MAUI Grid control. Learn about its features, setup process, column configuration, and creating custom column templates. Discover how to enable sorting, filtering, and selection for a dynamic and powerful data presentation in your apps. Watch now and become a DataGrid expert!"
    thumbnail-url="https://img.youtube.com/vi/XxUvA4fKHzU/maxresdefault.jpg"
    upload-date="2024-12-05T00:00:00Z"
    duration="PT20M27S"
    content-url="https://youtu.be/XxUvA4fKHzU"
    embed-url="https://www.youtube.com/embed/XxUvA4fKHzU">
</VideoMetadata>