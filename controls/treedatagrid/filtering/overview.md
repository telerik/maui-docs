---
title: Overview
page_title: .NET MAUI TreeDataGrid Documentation - Filtering Overview
description: Review the Telerik .NET MAUI TreeDataGrid Filtering documentation article to learn more about all built in filtering functions you can use.
position: 0
slug: treedatagrid-filtering-overview
---

{% if site.has_cta_panels == true %}
{% include cta-panel-small.html %}
{% endif %}

# .NET MAUI TreeDataGrid Filtering

The [Telerik UI for .NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) supports filtering operations either through the UI&mdash;by using the Filtering UI&mdash;or programmatically.

To use the built-in Filtering UI, the user must click the filtering icon present in each column's header.

## Filter Control Template

The Telerik TreeDataGrid allows you to apply custom filter control to the DataGrid column using the `FilterControlTemplate` property.

* `FilterControlTemplate`(`DataTemplate`)&mdash;Specifies the user defined template used for Filtering UI. The template must contain an instance of the `Telerik.Maui.Controls.DataGrid.DataGridFilterControlBase` class.

>tip Go to the [Filter Control Template]({%slug treedatagrid-filter-control-template%}) topic for detailed information about how to create a custom filter control.

## Programmatic Filtering

Programmatic filtering is achieved by adding different filter descriptors in the `FilterDescriptor` collection of the control. To learn more about programmatic filtering:

* Go to the [Programmatic Filtering]({%slug treedatagrid-programmatic-filtering%}) topic for detailed information about the provided filter descriptors.
* For an outline of all TreeDataGrid features, review the [.NET MAUI TreeDataGrid Overview]({%slug treedatagrid-overview%}) article.

## See Also

- [Filtering UI]({%slug treedatagrid-filtering-ui%})
- [Filter Control Template]({%slug treedatagrid-filter-control-template%})
- [Programmatic Filtering]({%slug treedatagrid-programmatic-filtering%})
