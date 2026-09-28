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

You can load new items in the DataGrid by using the `LoadOnDemand` event. The `LoadOnDemand` event handler receives the following parameters:
* The `sender` argument, which is of type `object`, but can be cast to the `RadDataGrid` type.
* A `LoadOnDemandEventArgs` object, which provides the `IsDataLoaded` (`bool`) property, indicating whether the data is loaded.

## Example

The following example demonstrates a sample setup that shows how to use the event:

1. Define the DataGrid in XAML:

<snippet id='datagrid-loadondemand-event-xaml'/>

2. Add the telerik namespace:

```xaml
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

2. Add sample data:

<snippet id='person-datamodel'/>

3. Define the `ViewModel`:

<snippet id='datagrid-loadondemand-event-viewmodel-csharp'/>

4. Handle the `LoadOnDemand` event:

<snippet id='datagrid-loadondemand-event-csharp'/>

>important For DataGrid LoadOnDemand event example, refer to the [SDKBrowser Demo application]({%slug sdkbrowser-app%}) and go to the **DataGrid > LoadOnDemand** category.

## See Also

- [Load On Demand Overview]({%slug datagrid-features-loadondemand%})
- [Load On Demand Collection]({%slug datagrid-load-on-demand-collection%})
- [Load On Demand Command]({%slug datagrid-load-on-demand-command%})
- [Load On Demand Styling]({%slug datagrid-load-on-demand-styling%})
