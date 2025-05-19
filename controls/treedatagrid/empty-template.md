---
title: Empty Template
page_title: .NET MAUI TreeDataGrid Documentation - Empty Template
description: Learn more about the Empty Template property of the TreeDataGrid control.
position: 9
slug: treedatagrid-empty-template
---

# .NET MAUI TreeDataGrid Empty Template

The [.NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) control provides the ability to specify a template when the `ItemsSource` is null or collection is empty.

It exposes the following properties:

* `EmptyContentTemplate`(`DataTemplate`)&mdash;Defines the content of the view which is shown when in the view has no items.

* `EmptyContentDisplayMode`&mdash;Defines the modes for displaying empty content. The property has two modes:
       - `ItemsSourceNull`&mdash;Displays the empty content view only when the `ItemsSource` is null.
       - `ItemsSourceNullOrEmpty`&mdash;Displays the empty content view when `ItemsSource` is null or when the source is empty (has zero items).

> As the TreeDataGrid inhertis from the DataGrid, for a runnable example with empty template scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **DataGrid > Empty Template** category. 

## See Also

 - [Filtering]({%slug datagrid-filtering-overview%})
 - [Grouping]({%slug datagrid-grouping-overview%})
 - [Selection]({%slug datagrid-selection-overview%})
