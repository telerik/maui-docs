---
title: Overview
page_title: .NET MAUI CollectionView Documentation - Load On Demand
description: Learn how to load data on demand in the Telerik UI for .NET MAUI CollectionView automatically or manually.
position: 0
slug: collectionview-load-on-demand
tags: loading data, .net maui, maui, collectionview, load data on demand
---

# .NET MAUI CollectionView Load Data on Demand

The Load Data on Demand feature optimizes the performance of the Telerik UI for .NET MAUI CollectionView control when operating with a large amount of items. The load-on-demand functionality allows you to load incremental data&mdash;either by a Button (manual) or by scrolling towards end (automatic).

## Configuration

Use the following configuration options to:

**1.** Control the `LoadOnDemand` feature by using the following properties:

* `IsLoadOnDemandEnabled` (`bool`)&mdash;Specifies whether the load-on-demand functionality is enabled. The default value is `false`.
* `IsLoadOnDemandActive` (`bool`)&mdash;Controls the loading indicator that is rendered when the data is retrieved asynchronously. Set it to `true` when an async operation is running and items are loading. Set it to `false` when the items are loaded. The default value is `false`.
* `LoadOnDemandMode` (enum of type `Telerik.Maui.LoadOnDemandMode`)&mdash;Specifies how the operation for loading more items is triggered. The available options are:
	* (Default) `Automatic`&mdash;The data is requested automatically when the user scrolls by the end of the CollectionView.
	* `Manual`&mdash;A button is rendered at the end of the CollectionView. The data is requested explicitly by pressing the button.

>tip When the `LoadOnDemandMode` is `Automatic` and grouping applies to the control, the `LoadOnDemandMode` transforms to `Manual`.

**2.** Control the number of pre-loaded items

You can control the minimum number of items loaded ahead by using the `LoadOnDemandBufferItemsCount` (`int`) property. The defined value indicates at which point the additional items will start loading. The default value is 10. 

>tip The `LoadOnDemandBufferItemsCount` works with `LoadOnDemandMode.Automatic`.

**3.** Customize the appearance of the automatic and manual UI element.

You can customize the appearance of the automatic and manual elements by using the following templates:

* `AutomaticLoadOnDemandTemplate` (`DataTemplate`)&mdash;Specifies the template of the view visualized for `Automatic` loading.
* `ManualLoadOnDemandTemplate` (`DataTemplate`)&mdash;Specifies the template of the view visualized for `Manual` loading.

For more information about the templates, including examples, review the [LoadOnDemand Templates]({%slug collectionview-load-on-demand-templates%}) article.

## Methods to Load Data on Demand

Use the following options to load data on demand:

* [`LoadOnDemandCollection`]({%slug collectionview-load-on-demand-collection%})
* [`LoadOnDemandCommand`]({%slug collectionview-load-on-demand-command%})
* [`LoadOnDemand` event]({%slug collectionview-load-on-demand-event%})

The three approaches work with `Automatic` and `Manual` `LoadOnDemandMode`.

## See Also

- [Load On Demand Collection]({%slug collectionview-load-on-demand-collection%})
- [Load On Demand Command]({%slug collectionview-load-on-demand-command%})
- [Load On Demand Event]({%slug collectionview-load-on-demand-event%})
- [Customize the Load On Demand Manual and Automatic Loading Indicators]({%slug collectionview-load-on-demand-templates%})