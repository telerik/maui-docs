---
title: DataTable Support
page_title: .NET MAUI DataGrid Documentation - DataTable Support
description: "Learn how to bind the Telerik UI for .NET MAUI DataGrid to a DataTable and how to provide support for all available features such as filtering, sorting, grouping, CRUD operations, and commands."
position: 14
slug: datagrid-datatable-support
---

# .NET MAUI DataGrid Support for DataTable

As of the Telerik UI for .NET MAUI 5.1.0 version, the DataGrid provides full and seamless support for all its features in the DataTable.

The component enables you to bind it to the DataTable and you can also add, remove, select, and edit DataGrid items, and update the DataGrid `ItemsSource`. All available DataGrid commands and operations, like filtering, sorting, grouping, and selection, are fully functioning when the DataGrid is bound to a DataTable.

## Binding

The following example shows a sample DataGrid `ItemsSource` binding to a DataTable:

**1.** Define the DataGrid.

<snippet id='datagrid-datatable-binding'/>

**2.** Add the namespace.

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Set the `ViewModel`.

<snippet id='datagrid-datatable-viewmodel'/>

> For a full data-binding implementation of a DataGrid to a DataTable, see the `DataGrid/DataTable` folder of the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## Filtering, Sorting, and Grouping

When using a DataTable, you can filter, group, and sort the data inside the DataGrid through the UI or programmatically.

## CRUD Operations

All CRUD operations, such as adding, removing, and updating the data inside the DataGrid, are supported when the DataGrid is bound to a DataTable.

**1.** Define the DataGrid.

<snippet id='datagrid-datatable-crud'/>

**2.** Add a row.

<snippet id='datagrid-datatable-add-row'/>

 **3.** Delete a row.

<snippet id='datagrid-datatable-delete-data'/>

 **4.** Update the data.

<snippet id='datagrid-datatable-update-data'/>

> For a full CRUD operations implementation of a DataGrid when bound to a DataTable, see the `DataGrid/DataTable` folder of the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## Commands

All commands supported by the DataGrid are fully applicable when the component is bound to a DataTable. For the full list, see the article with the [available commands in the DataGrid]({%slug datagrid-commands-overview%}).

> For a sample implementation of the DataGrid commands in a DataTable, see the `DataGrid/DataTable` folder of the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## Additional Resources

- [.NET MAUI DataGrid Product Page](https://www.telerik.com/maui-ui/datagrid)
- [.NET MAUI DataGrid Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Filtering UI in the Telerik UI for .NET MAUI DataGrid]({%slug datagrid-filtering-ui%})
- [Programmatic Filtering in the DataGrid]({%slug datagrid-programmatic-filtering%})
- [Grouping in the DataGrid]({%slug datagrid-grouping-overview%})
- [Styling the Appearance of the DataGrid]({%slug datagrid-styling%})
