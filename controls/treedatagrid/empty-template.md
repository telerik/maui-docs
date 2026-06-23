---
title: Empty Template
page_title: .NET MAUI TreeDataGrid Documentation - Empty Template
description: Learn how to display a custom empty template in the Telerik UI for .NET MAUI TreeDataGrid when ItemsSource is null or empty.
position: 18
slug: treedatagrid-empty-template
---

# .NET MAUI TreeDataGrid Empty Template

The [.NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) control provides the ability to specify a template when the `ItemsSource` is null or collection is empty.

It exposes the following properties:

* `EmptyContentTemplate`(`DataTemplate`)&mdash;Defines the content of the view which is shown when in the view has no items.

* `EmptyContentDisplayMode`&mdash;Defines the modes for displaying empty content. The property has two modes:
       - `ItemsSourceNull`&mdash;Displays the empty content view only when the `ItemsSource` is null.
       - `ItemsSourceNullOrEmpty`&mdash;Displays the empty content view when `ItemsSource` is null or when the source is empty (has zero items).

> As the TreeDataGrid inherits from the DataGrid, for a runnable example with empty template scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **DataGrid > Empty Template** category. 

## See Also

 - [Filtering]({%slug treedatagrid-filtering-overview%})
 - [Selection]({%slug treedatagrid-selection-overview%})
