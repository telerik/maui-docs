---
title: Empty Template
page_title: .NET MAUI DataGrid Documentation - Empty Template
description: "Learn more about the Empty Template property of the DataGrid control."
position: 9
slug: datagrid-empty-template
---

# .NET MAUI DataGrid Empty Template

The `DataGrid` control provides the ability to specify a template when the `ItemsSource` is null or collection is empty.

It exposes the following properties:

* `EmptyContentTemplate`(`DataTemplate`)&mdash;Defines the content of the view which is shown when in the view has no items.

* `EmptyContentDisplayMode`&mdash;Defines the modes for displaying empty content. The property have two modes:
       - `ItemsSourceNull`&mdash;Displays the empty content view only when the `ItemsSource` is null.
       - `ItemsSourceNullOrEmpty`&mdash;Displays the empty content view when `ItemsSource` is null or when the source is empty(has zero items).


## Example:

**1.** Add DataGrid definition in XAML:

<snippet id ='datagrid-empty-template-xaml'/>

**2.** Add `DataTemplate` Resources:

<snippet id='datagrid-empty-template-resources'/>

## See Also

 - [Filtering]({%slug datagrid-filtering-overview%})
 - [Grouping]({%slug datagrid-grouping-overview%})
 - [Selection]({%slug datagrid-selection-overview%})
