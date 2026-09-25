---
title: Overview
page_title: .NET MAUI DataGrid Documentation - Load On Demand
description: Learn how to load large datasets incrementally in the Telerik UI for .NET MAUI DataGrid to improve performance and save computing resources.
components: ["datagrid"]
position: 0
slug: datagrid-features-loadondemand
tags: loading data, .net maui, maui, datagrid, load data on demand
---

# .NET MAUI DataGrid Load On Demand

The [Telerik UI for .NET MAUI DataGrid]({%slug datagrid-overview%}) enables you to improve its performance and save computing resources, by loading data in the `RadDataGrid` when the control is already displayed.

To load a large data set on mobile devices, you can use incremental data loading at the time when the user requires the items to be visualized.

## Modes

The DataGrid provides the following data-loading modes, which are present in the `LoadOnDemandMode` enumeration:

* `Automatic`&mdash;The load-on-demand mechanism is activated when you scroll down near the last item present in the viewport.

  >important To control when the items will start loading, set the `LoadOnDemandBufferItemsCount` property. It indicates at which point the additional items will start loading. For example, setting it to `20` will cause the new items to be loaded when you have scrolled the DataGrid, so that only 20 of the originally loaded items are left below.

* `Manual`&mdash;A **Load More** button is present at the bottom of the DataGrid. Tapping it loads additional items based on the approach you have chosen for loading the items (through the collection, the event, or the command).

>tip When the `LoadOnDemandMode` is `Automatic` and grouping applies to the control, the `LoadOnDemandMode` transforms to `Manual`.

## Methods to Load Data on Demand

Use the following options to load data on demand, depending on your application requirements:

* [`LoadOnDemandCollection`]({%slug datagrid-load-on-demand-collection%})
* [`LoadOnDemand` event]({%slug datagrid-load-on-demand-event%})
* [`LoadMoreData` command]({%slug datagrid-load-on-demand-command%})

## Styling

To customize the loading indicator and the **Load More** row, review the [Load On Demand Styling]({%slug datagrid-load-on-demand-styling%}) article.

## Additional Resources

- [.NET MAUI DataGrid Product Page](https://www.telerik.com/maui-ui/datagrid)
- [.NET MAUI DataGrid Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Filtering]({%slug datagrid-filtering-overview%})
- [Grouping]({%slug datagrid-grouping-overview%})
- [Selection]({%slug datagrid-selection-overview%})
