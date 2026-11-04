---
title: Events
meta_title: .NET MAUI RefreshView Documentation - Events
description: Learn how to handle the Pulling, Refreshing, and Refreshed events of the Telerik UI for .NET MAUI RefreshView to respond to pull gestures.
components: ["refreshview"]
position: 8
slug: refreshview-events
---

# .NET MAUI RefreshView Events

The Telerik UI for .NET MAUI RefreshView raises events while the user pulls the content, when a refresh starts, and when a refresh completes. Handle these events to track the pull progress, cancel a gesture, or load data.

## Pulling

The RefreshView raises the `Pulling` event while the user pulls the content and before a refresh starts. The `Pulling` event handler receives the following parameters:

* The `sender` argument, which is of type `object`, but can be cast to the `RadRefreshView` type.
* A `Telerik.Maui.Controls.RefreshView.RefreshViewPullingEventArgs` object, which provides the following properties:
    * `Progress` (`double`)&mdash;Gets the normalized progress toward the refresh threshold, from `0.0` to `1.0`.
    * `Cancel` (`bool`)&mdash;Specifies whether to cancel the current pull gesture. After cancellation, the RefreshView continues to handle the gesture.

## Refreshing

The RefreshView raises the `Refreshing` event when a refresh starts. The event also occurs when you start a refresh by setting `IsRefreshing` to `true`. The `Refreshing` event handler receives the following parameters:

* The `sender` argument, which is of type `object`, but can be cast to the `RadRefreshView` type.
* An `EventArgs` object.

Load the data in the `Refreshing` event handler, and then set `IsRefreshing` to `false` to end the refresh.

## Refreshed

The RefreshView raises the `Refreshed` event when a refresh completes. The `Refreshed` event handler receives the following parameters:

* The `sender` argument, which is of type `object`, but can be cast to the `RadRefreshView` type.
* An `EventArgs` object.

## Handle the RefreshView Events

The following example demonstrates how to display the pull progress, cancel a pull gesture after half of the pulling threshold, and log the `Refreshing` and `Refreshed` events.

1. Define the RefreshView in XAML:

    <snippet id='refreshview-events' />

2. Define the event handlers:

    <snippet id='refreshview-events-handlers' />

> tip For a runnable example demonstrating the RefreshView events, see the [SDKBrowser Demo Application]({% slug sdkbrowser-app %}) and go to the **RefreshView > Events** category.

## See Also

- [RefreshView Commands]({% slug refreshview-commands %})
- [Refresh State]({% slug refreshview-refresh-state %})
- [Thresholds]({% slug refreshview-thresholds %})
