---
title: DataTable Support
page_title: .NET MAUI DataGrid Documentation - DataTable Support
description: Check our DataTable Support documentation article for Telerik DataGrid for .NET MAUI control.
position: 11
slug: datagrid-datatable-support
---

# DataTable Support

With SP1 2023 Release of Telerik UI for .NET MAUI, **DataGrid** fully supports binding to a `DataTable`. 

All DataGrid features work with DataTable. You can add, remove, select, edit item(s) and update the DataGrid's ItemsSource. In addition, all available commands and operations like filtering, sorting, grouping, selection work when the DataGrid is bound to a DataTable. 

## Bind to DataTable

1. DataGrid definition:

<snippet id='datagrid-datatable-binding'/>

 2. Add the namespace:

 ```XAML
 xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

3. The ViewModel used: 

 <snippet id='datagrid-datatable-view-model'/>

## Filtering, Sorting, Grouping

When using DataTable you can filter, group, sort the data inside the DataGrid through the UI or programmatically.

## CRUD Operations with DataTable

All operations like add, remove, update data inside the DataGrid is supported when the Source is from DataTable.

DataGrid definition:

<snippet id='datagrid-datatable-crud'/>

 ### Add Row

<snippet id='datagrid-datatable-add-row'/>

 ### Delete Row

<snippet id='datagrid-datatable-delete-data'/>

 ### Update Data

<snippet id='datagrid-datatable-update-data'/>

### Examples

A sample Bind to DataTable example can be found in the DataGrid/DataTable folder of the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

A sample CRUD Operations example can be found in the DataGrid/DataTable folder of the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

A sample Commands example can be found in the DataGrid/DataTable folder of the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## See Also

- [Filtering UI]({%datagrid-filtering-ui%})
- [Programmatic Filtering]({%datagrid-programmatic-filtering%})
- [Grouping]({%datagrid-grouping-ui%})


