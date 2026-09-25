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

To load data on demand by using a collection, feed the `RadDataGrid` with a collection of type `LoadOnDemandCollection`. `LoadOnDemandCollection` is a generic type, so you need to specify the type of objects it will contain. The type extends the `ObservableCollection<T>` class and expects a `Func<CancellationToken, IEnumerable>` in the constructor.

## Example

The following example demonstrates a simple setup that shows how to use the collection:

<snippet id='datagrid-loadondemand-collection-csharp'/>

In the example, the `Items` property is declared as follows:

<snippet id='datagrid-loadondemand-collection-property-csharp'/>

## See Also

- [Load On Demand Overview]({%slug datagrid-features-loadondemand%})
- [Load On Demand Event]({%slug datagrid-load-on-demand-event%})
- [Load On Demand Command]({%slug datagrid-load-on-demand-command%})
- [Load On Demand Styling]({%slug datagrid-load-on-demand-styling%})
