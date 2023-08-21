---
title: Load on Demand
page_title: .NET MAUI ListView Documentation - Load on Demand
description: Learn more about the load on demand functionallity that the Telerik UI for .NET MAUI ListView control provides.
position: 9
previous_url: /controls/listview/listview-features-load-on-demand
slug: listview-features-load-on-demand
---

# .NET MAUI ListView Load on Demand

Loading a large data set on a mobile device has its challenges. One of the most popular approaches is using incremental data loading when the items need to be visualized. The ListView does this by using its load-on-demand functionality.

## Configuration

The following properties control the `LoadOnDemand` feature:

* `IsLoadOnDemandEnabled`(`bool`)&mdash;Used to enable the load on demand mechanism of the ListView.
* `IsLoadOnDemandActive` (`bool`)&mdash;Used to control the loading indicator that is rendered when the data is retrieved asynchronously. Set it to `True` when an async operation is running and items are loading. Set it to `False` when the items are loaded.
* `LoadOnDemandMode`&mdash;Used to set the loading mode. You can select between:
  * `Automatic`&mdash;The data is requested automatically when you scroll near the end of the ListView.
  * `Manual`&mdash;A button is rendered at the end of the ListView. The data is requested explicitly by pressing the button.

## Methods to Load Data on Demand

Three options to load the data on demand, regardless of whether you use the `Automatic` or `Manual` loading mode:

* [Create a `ListViewLoadOnDemandCollection` instance as a source and pass it to the ListView Items Source property](#using-loadondemandcollection).
* [Subscribe to the LoadOnDemand event and add the loaded data to the source](#using-loadondemand-event).
* [Use the LoadOnDemand User Command and add the loaded data to the source](#using-loadondemand-command).

>note All three approaches for loading items on demand in the ListView work with both the automatic and manual `LoadOnDemandMode`.


### Using LoadOnDemandCollection

To load items on demand, you can use the `ListViewLoadOnDemandCollection` and set it as an `ItemsSource` for the ListView. The `ListViewLoadOnDemandCollection` accepts an action in the constructor and this action is later executed by the ListView in a non-UI thread when new items are requested.

The example below demonstrates how to use the `LoadOnDemandCollection`:

Define a sample `ViewModel` class with the `Source` property of type `ListViewLoadOnDemandCollection`:

<snippet id='listview-loadondemand-loadondemandcollection-viewmodel'/>

Define the ListView instance and bind its `ItemsSource` to the data in the `ViewModel`:

<snippet id='listview-loadondemand-loadondemandcollection-declaration'/>

Add the `telerik` namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

### Using LoadOnDemand Event

Another way to handle loading more items is to use the `LoadOnDemand` event. This event is raised on a UI thread, so in the event handler you can add items right away or asynchronously:

* In case the data is available right away, add the items to the ListView `ItemsSource` in the `LoadOnDemand` event handler.
* If you require an async operation, set the `IsLoadOnDemandActive` property of the ListView to `True`. This notifies the ListView that it must display the loading indicator. Then an async call can be initiated to get the data. When the new items are ready, you must set the `IsLoadOnDemandActive` property to `False` again to notify the ListView that the load-on-demand operation is completed.

The example below demonstrates how to use the LoadOnDemand event:

Define the ListView:

<snippet id='listview-loadondemand-loadondemandeventauto-declaration' />

Set the ListView `ItemsSource` , for example in the page constructor:

<snippet id='listview-loadondemand-loadondemandeventauto-bind'/>

Add the following event handler:

<snippet id='listview-loadondemand-loadondemandeventauto-event'/>

### Using LoadOnDemand Command

This approach is similar to [using the LoadOnDemand event](#using-loadondemand-event), but in this case, the load-on-demand is handled in the `ViewModel` through the `LoadOnDemandUserCommand` exposed by the ListView. In the `Execute` method of the command, you can add items right away or asynchronously:

* If the data is available right away, add the items to the ListView `ItemsSource` in the `LoadOnDemand` command `Execute` method.
* If you require an async operation, set the `IsLoadOnDemandActive` property of the ListView to `True`. This notifies the ListView that it must display the loading indicator. Then an async call can be initiated to get the data. When the new items are ready, you must set the `IsLoadOnDemandActive` property to `False` again to notify the ListView that the load-on-demand operation is completed. You can control the behavior of `IsLoadOnDemandActive` through a binding to a boolean property in the `ViewModel` class.

The example below demonstrates how to use the `LoadOnDemand` command:

Create a `ViewModel` class with a `LoadItemsCommand` as well as the `IsLoadingMoreItems` property:

<snippet id='listview-loadondemand-loadondemandcommand-viewmodel'/>

Define the `RadListView` instance in XAML with the `ListViewUserCommand` defined as well as the `IsLoadOnDemandActive` property bound to the boolean property in the `ViewModel`:

<snippet id='listview-loadondemand-loadondemandcommand-declaration'/>

Add the `telerik` namespaces:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## Advanced Options

You can also use the ListView options for performing advanced control over its load-on-demand feature.  

### Control the Number of Pre-loaded Items

This feature works in conjunction with the [LoadOnDemandMode.Automatic mode of the ListView]({%slug listview-features-load-on-demand%}#automatic-mode). You can control the minimum number of items loaded ahead through ListView `LoadOnDemandBufferItemsCount` property. By default, the property is for 10 items. When ListView requests an item in the buffer, it will trigger a new loading batch.

### Change the Appearance of the Manual Load Button

This feature works in conjunction with the [LoadOnDemandMode.Manual mode of the ListView]({%slug listview-features-load-on-demand%}#manual-loading-mode). You can control the content of the Load More Button through the `LoadOnDemandItemTemplate` property.

<snippet id='listview-loadondemand-loadondemandcustomizations-lodbutton' />

### Change the Appearance of the Manual Loading Indicator

This feature works in conjunction with the [LoadOnDemandMode.Manual mode of the ListView]({%slug listview-features-load-on-demand%}#manual-loading-mode).

You can control the content of the Loading Indicator through the `LoadingOnDemandItemTemplate` property.

<snippet id='listview-loadondemand-loadondemandcustomizations-loadingindicator'/>

## See Also

- [Events]({%slug listview-features-events%})
- [Selection]({%slug listview-features-selection%})
- [Reordering]({%slug listview-features-reorder-items%})
