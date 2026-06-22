---
title: Overview
page_title: .NET MAUI DataGrid Documentation - Filtering Overview
description: Learn how to filter data in the Telerik UI for .NET MAUI DataGrid using the built-in Filtering UI or programmatic filter descriptors.
position: 0
previous_url: /controls/datagrid/datagrid-filtering-overview
slug: datagrid-filtering-overview
---

# .NET MAUI DataGrid Filtering

The [Telerik UI for .NET MAUI DataGrid]({%slug datagrid-overview%}) supports filtering operations either through the UI&mdash;using the built-in Filtering UI&mdash;or programmatically by adding filter descriptors.

Filtering enables users to narrow down the displayed data by applying conditions to one or more columns. The DataGrid provides both a user-friendly Filtering UI and a powerful programmatic API for advanced scenarios.

## Filtering UI

> The Filtering UI appears when clicking the filtering icon in each column's header.

![Telerik .NET MAUI DataGrid Filtering UI](../filtering/images/datagrid-filteringui-platforms.png)

The Filtering UI supports text, numeric, date, and boolean filter operators out of the box. Users can combine multiple conditions using logical AND/OR operators.

## Filter Control Template

The Telerik DataGrid allows you to apply custom filter control to the DataGrid column using the `FilterControlTemplate` property.

* `FilterControlTemplate`(`DataTemplate`)&mdash;Specifies the user defined template used for Filtering UI. The template must contain an instance of the `Telerik.Maui.Controls.DataGrid.DataGridFilterControlBase` class.

>tip Go to the [Filter Control Template]({%slug datagrid-filter-control-template%}) topic for detailed information about how to create a custom filter control.

## Programmatic Filtering

Programmatic filtering is achieved by adding different filter descriptors in the `FilterDescriptor` collection of the control.

>tip Go to the [Programmatic Filtering]({%slug datagrid-programmatic-filtering%}) topic for detailed information about the provided filter descriptors.

>tip For an outline of all DataGrid features review the [.NET MAUI DataGrid Overview]({%slug datagrid-overview%}) article.

## See Also

- [Filtering UI]({%slug datagrid-filtering-ui%})
- [Filter Control Template]({%slug datagrid-filter-control-template%})
- [Programmatic Filtering]({%slug datagrid-programmatic-filtering%})
