---
title: Overview
page_title: .NET MAUI DataGrid Documentation - Filtering Overview
description: "Review the Telerik .NET MAUI DataGrid Filtering documentation article to learn more about all built in filtering functions you can use."
position: 0
previous_url: /controls/datagrid/datagrid-filtering-overview
slug: datagrid-filtering-overview
---

# .NET MAUI DataGrid Filtering

The [Telerik UI for .NET MAUI DataGrid]({%slug datagrid-overview%}) supports filtering operations either through the UI - using the Filtering UI or programmatically.

## Filtering UI

> The filtering UI appears when clicking the filtering icon in each column's header.

![Telerik .NET MAUI DataGrid Filtering UI](../filtering/images/datagrid-filteringui-platforms.png)

## Filter Control Template

The Telerik DataGrid allows you to apply custom filter control to the DataGrid column using the `FilterControlTemplate` property.

* `FilterControlTemplate`(`DataTemplate`)&mdash;Specifies the user defined template used for Filtering UI. The template must contain an instance of the `Telerik.Maui.Controls.Compatibility.DataGrid.DataGridFilterControlBase` class.

>tip Go to the [Filter Control Template]({%slug datagrid-filter-control-template%}) topic for detailed information about how to create a custom filter control.

## Programmatic Filtering

Programmatic filtering is achieved by adding different filter descriptors in the `FilterDescriptor` collection of the control.

>tip Go to the [Programmatic Filtering]({%slug datagrid-programmatic-filtering%}) topic for detailed information about the provided filter descriptors.

>tip For an outline of all DataGrid features review the [.NET MAUI DataGrid Overview]({%slug datagrid-overview%}) article.

## See Also

- [Filtering UI]({%slug datagrid-filtering-ui%})
- [Filter Control Template]({%slug datagrid-filter-control-template%})
- [Programmatic Filtering]({%slug datagrid-programmatic-filtering%})
