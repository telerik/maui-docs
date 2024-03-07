---
title: Migrating from Xamarin
page_title: .NET MAUI DataGrid Documentation - Migrate from Xamarin
description: Learn how to migrate from Xamarin.Forms DataGrid to .NET MAUI DataGrid control.
position: 100
tags: dot net maui, .net maui vs xamarin, maui vs xamarin, net maui vs xamarin, migration, xamarin.forms
slug: datagrid-xamarin-migration
---

# Migrate from Xamarin.Forms DataGrid to .NET MAUI DataGrid

The Telerik UI for .NET MAUI DataGrid preserves the same API as its Xamarin counterpart except for the configuration options listed in this article.

The tables in the following sections list any differences between the APIs of the Xamarin.Forms DataGrid and .NET MAUI DataGrid.

## Migrate the Namespaces

| Control | Control name | C# Namespace| XAML Namespcace |
| --------------- | --------------- | --------------- | --------------------------------------------------- |
| Xamarin DataGrid | `RadDataGrid` | xmlns:telerikDataGrid="clr-namespace:Telerik.XamarinForms.DataGrid;assembly=Telerik.XamarinForms.DataGrid" | using Telerik.XamarinForms.DataGrid; |
| .NET MAUI DataGrid | `RadDataGrid` |  xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls.Compatibility.DataGrid; |

## API Changes

| Xamarin DataGrid | .NET MAUI DataGrid |
| ------------- | --------------- |
| N/A | Row Details |
| N/A | Aggregates |
| N/A | Frozen Colums |
| N/A | Column Resizing |
| N/A | Column Footer |
| N/A | Column Reordering |
| N/A | Keyboard Navigation |
| N/A | DynamicObject |
| N/A | ExpandoObject  |
| N/A | Built-in Search Functionality  |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
* [.NET MAUI DataGrid Product Page](https://www.telerik.com/maui-ui/datagrid)
* [.NET MAUI DataGrid Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
