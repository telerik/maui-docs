---
title: Overview
page_title: .NET MAUI DataGrid Documentation - Filtering Overview
description: "Review the Telerik .NET MAUI DataGrid Filtering documentation article to learn more about all built in filtering functions you can use."
position: 0
previous_url: /controls/datagrid/datagrid-filtering-overview
slug: datagrid-filtering-overview
---

# .NET MAUI DataGrid Filtering

**Telerik UI for .NET MAUI DataGrid** supports filtering operations either through the UI - using the Filtering UI or programmatically.

![Filtering UI](../filtering/images/datagrid-filtering-ui.gif)

## Filtering UI

> Filtering UI appears when clicking on the filtering icon on each column's header'.

## FilterControl Template

The Telerik DataGrid allows you to apply filtering to the datagrid column using the FilterControlTemplate property.

* `FilterControlTemplate`(`DataTemplate`)&mdash;Specifies the user defined template used for Filtering UI. The template must contain an instance of the `Telerik.Maui.Controls.Compatibility.DataGrid.DataGridFilterControlBase` class.

## Programmatic Filtering

Programmatic filtering is achieved by adding different filter descriptors in the `FilterDescriptor` collection of the control.
