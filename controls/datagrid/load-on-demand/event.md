---
title: Event
page_title: .NET MAUI DataGrid Documentation - Load On Demand Event
description: Learn how to load data on demand in the Telerik UI for .NET MAUI DataGrid by using the LoadOnDemand event.
components: ["datagrid"]
position: 2
slug: datagrid-load-on-demand-event
tags: loading data, .net maui, maui, datagrid, load data on demand, loadondemand event
---

# .NET MAUI DataGrid LoadOnDemand Event

You can load new items in the DataGrid by using the `LoadOnDemand` event. The event uses `LoadOnDemandEventArgs` arguments through which you need to indicate when the data is loaded by setting the `IsDataLoaded` (`bool`) property.

## Example

The following example demonstrates how to handle the event:

<snippet id='datagrid-loadondemand-event-csharp'/>

## See Also

- [Load On Demand Overview]({%slug datagrid-features-loadondemand%})
- [Load On Demand Collection]({%slug datagrid-load-on-demand-collection%})
- [Load On Demand Command]({%slug datagrid-load-on-demand-command%})
- [Load On Demand Styling]({%slug datagrid-load-on-demand-styling%})
