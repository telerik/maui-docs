---
title: Load On Demand
page_title: .NET MAUI TreeDataGrid Documentation - Load on Demand
description: Learn more about the available modes and approaches to load huge sets of data in the Telerik UI for .NET MAUI TreeDataGrid to improve the performance of the component and save computing resources.
position: 13
slug: treedatagrid-loadondemand
---

# .NET MAUI DataGrid Load On Demand

The  [Telerik UI for .NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) enables you to improve its performance and save computing resources, by loading data in the `RadTreeDataGrid` when the control is already displayed.

To load a large data set on mobile devices, you can use incremental data loading at the time when the user required the items to be visualized.

## Modes

The DataGrid provides the following data-loading modes, which are present in the `LoadOnDemandMode` enumeration:

* `Automatic`&mdash;The load-on-demand mechanism is activated when you scroll down near the last item present in the viewport.

  >important To control when the items will start loading, set the `LoadOnDemandBufferItemsCount` property. It indicates at which point the additional items will start loading. For example, setting it to `20` will cause the new items to be loaded when you have scrolled the DataGrid, so that only 20 of the originally loaded items are left below.

* `Manual`&mdash;A **Load More** button is present at the bottom of the DataGrid. Clicking it will load additional items based on the approach you have chosen for loading the items (through the event, the command, or the collection).

>tip When the `LoadOnDemandMode` is `Automatic` and grouping applies to the control, the `LoadOnDemandMode` transforms to `Manual`.

## Approaches

The DataGrid supports the following options for using its load-on-demand feature, depending on your application requirements:

 * [Using the `LoadOnDemand` collection](#loadondemand-collection)
 * [Using the `LoadOnDemand` event](#loadondemand-event)
 * [Using the `LoadMoreData` command](#loadmoredata-command)

### LoadOnDemand Collection

To use this approach, you have to feed the `RadDataGrid` with a collection of type `LoadOnDemandCollection`. `LoadOnDemandCollection` is a generic type, so you need to point the type of objects it will contain. The type extends the `ObservableCollection<T>` class and expects a `Func<CancellationToken, IEnumerable>` in the constructor.

### LoadOnDemand Event

You can load new items by utilizing the `LoadOnDemand` event. The event uses `LoadOnDemandEventArgs` arguments through which you need to indicate when the data is loaded by setting the `IsDataLoaded`(`bool`) property.

### LoadMoreData Command

The `LoadMoreData` command is another alternative which you can use and which is suitable for MVVM scenarios.

>important Invoking the `ShowLoadOnDemandLoadingIndicator` and `HideLoadOnDemandLoadingIndicators` is a notable part as without calling these methods, the `BusyIndicator` used for the functionality will not be visualized.

## Styling

Besides the different approaches for loading the data, the DataGrid exposes several mechanisms related to the styling of the functionality which you can use according to the approach you have chosen.

### Load-More-Button Row

The `LoadOnDemandRowStyle` property can be used to style the appearance of the row that contains the **Load More** button when the `LoadOnDemandMode` is `Manual`.

The custom style is of type `Style` with target type `DataGridLoadOnDemandRowAppearance`:

### Load-More-Button Row Template

The `LoadOnDemandRowTemplate` property can be used to set the template of the row that contains the **Load More** button when the `LoadOnDemandMode` is `Manual`.

## Examples

For runnable examples with the TreeDataGrid Load On Demand options, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **DataGrid > Load On Demand** category. Replace the examples with `TreeDataGrid` and set a `ViewModel` and Data models with hierarchical data structrue. 

## Additional Resources

- [.NET MAUI TreeDataGrid Product Page](https://www.telerik.com/maui-ui/treedatagrid)
- [.NET MAUI TreeDataGrid Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Sorting .NET MAUI TreeDataGrid Records]({%slug treedatagrid-sorting%})
- [Filtering .NET MAUI TreeDataGrid Records]({%slug treedatagrid-filtering-overview%})
