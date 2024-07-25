---
title: Command
page_title: .NET MAUI CollectionView Documentation - Load On Demand Command
description: Learn how to load data on demand in the Telerik UI for .NET MAUI CollectionView automatically or manually by using the exposed command.
position: 2
slug: collectionview-load-on-demand-command
tags: loading data, .net maui, maui, collectionview, load data on demand, loading command
---

# .NET MAUI CollectionView LoadOnDemand Command

The `LoadOnDemandCommand` (of type `ICommand`) is another alternative which you can use for loading data on demand. This alternative is suitable for MVVM scenarios.

## Example

The following example demonstrates a simple setup that shows how to use the command:

**1.** Create a sample model:

<snippet id='person-datamodel' />

**2.** Define the CollectionView control:

<snippet id='collectionview-loadondemand-command' />

**3.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**4.** Create a `ViewModel` and define a command that is bound to the `RadCollectionView.LoadOnDemandCommand` property:

<snippet id='collectionview-loadondemand-command-viewmodel' />

This is the result:

## See Also

- [Load On Demand Collection]({%slug collectionview-load-on-demand-collection%})
- [Load On Demand Event]({%slug collectionview-load-on-demand-event%})
- [Customize the Load On Demand Manual and Automatic Loading Indicators]({%slug collectionview-load-on-demand-templates%})