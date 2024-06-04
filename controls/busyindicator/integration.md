---
title: Integration
page_title: .NET MAUI BusyIndicator Documentation - CollectionView Integration
description: Learn more about the option to integrate BusyIndacator with CollectionView control.
position: 2
previous_url: /controls/busyindicator/integrate-with-listview
slug: busyindicator-integration
---

# .NET MAUI BusyIndicator Integration with CollectionView

The Telerik BusyIndicator for .NET MAUI is useful when you want to display a notification to the end-users of the application while a long-running operation, such as loading data from a service, is currently in progress.

The example below demonstrates a sample integration of the BusyIndicator with the CollectionView control. The CollectionView loads its data asynchronously (this is simulated for the purpose of the example) and while the load operation is taking place, the `IsBusy` state of the BusyIndicator is enabled.

**1.** Create a sample `Book` class used for the `ItemsSource` of the CollectionView:

<snippet id='busyindicator-withcollectionview-model' />

**2.** Add a `ViewModel` class, which provides the following:

  * A collection of `Book` objects that is used for binding the CollectionView.
  * A Boolean `IsLoading` property to control the Busy state of the BusyIndicator.
  * A `LoadData` command that starts the loading of the items.

<snippet id='busyindicator-withcollectionview-csharp' />

**3.** Add the CollectionView and the BusyIndicator controls to the view:

<snippet id='busyindicator-withcollectionview-xaml' />

**4.** Set the `ViewModel` class as `BindingContext` of the page:

<snippet id='busyindicator-withcollectionview-setvm' />

The gif below shows the result.

![Telerik UI for .NET MAUI BusyIndicator Integration](images/busyindicator-integration.gif)

## See Also

- [BusyIndicator Animations]({% slug busyindicator-animations %})
