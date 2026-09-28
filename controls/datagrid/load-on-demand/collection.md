---
title: Collection
page_title: .NET MAUI DataGrid Documentation - Load On Demand Collection
description: Learn how to load data on demand in the Telerik UI for .NET MAUI DataGrid by using the LoadOnDemandCollection.
components: ["datagrid"]
position: 1
slug: datagrid-load-on-demand-collection
tags: loading data, .net maui, maui, datagrid, load data on demand, loadondemandcollection
---

# .NET MAUI DataGrid LoadOnDemand Collection

To load data on demand by using a collection, feed the `RadDataGrid` with a collection of type `Telerik.Maui.LoadOnDemandCollection`. The `LoadOnDemandCollection` is a generic type, so you need to specify the type of objects it will contain. The type extends the `ObservableCollection<T>` class and expects a `Func<CancellationToken, IEnumerable>` in the constructor.

## Example

The following example demonstrates a sample setup that shows how to use the collection:

1. Define the DataGrid in XAML:

<snippet id='datagrid-loadondemand-xaml'/>

2. Add the telerik namespace:

```xaml
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

2. Add sample data:

<snippet id='person-datamodel'/>

3. Declare the `Items` property:

<snippet id='datagrid-loadondemand-collection-csharp'/>

4. Set data to the `Items` collection:

<snippet id='datagrid-loadondemand-collection-csharp'/>

>important For DataGrid LoadOnDemandCollection example, refer to the [SDKBrowser Demo application]({%slug sdkbrowser-app%}) and go to the **DataGrid > LoadOnDemand** category.

## See Also

- [Load On Demand Overview]({%slug datagrid-features-loadondemand%})
- [Load On Demand Event]({%slug datagrid-load-on-demand-event%})
- [Load On Demand Command]({%slug datagrid-load-on-demand-command%})
- [Load On Demand Styling]({%slug datagrid-load-on-demand-styling%})
