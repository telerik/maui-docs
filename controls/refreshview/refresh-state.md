---
title: Refresh State
meta_title: .NET MAUI RefreshView Documentation - Refresh State
description: Learn how to start and stop a refresh programmatically and turn the pull gesture on or off in the Telerik UI for .NET MAUI RefreshView.
components: ["refreshview"]
tags: .net maui, telerik .net maui, ui for .net maui, refreshview, microsoft .net maui
position: 0
slug: refreshview-refresh-state
---

# .NET MAUI RefreshView Refresh State

The RefreshView refresh state defines whether a refresh is in progress and whether the user can start a refresh with a pull gesture. Use these settings to start a refresh from code, for example, when the page loads, or to block the pull gesture while the data source is unavailable.

## Control the Refresh State

To control the refresh state of the RefreshView, use the following properties:

* `IsRefreshing` (`bool`)&mdash;Defines whether a refresh is in progress. Set the property to `true` to start a refresh from code. Set it to `false` to end the refresh and hide the indicator.
* `IsRefreshEnabled` (`bool`)&mdash;Defines whether pull gestures can start a refresh. When the value is `false`, the pull gesture is unavailable, but you can still start a refresh by setting `IsRefreshing` to `true`.

The RefreshView doesn't end a refresh on its own. When your data is loaded, set `IsRefreshing` to `false`. When the refresh ends, the RefreshView raises the `Refreshed` event.

## Start and Stop a Refresh Programmatically

The following example demonstrates how to start and stop a refresh with buttons and how to turn the pull gesture on or off with a checkbox.

1. Define the RefreshView in XAML:

    <snippet id='refreshview-refresh-state' />

2. Add the `telerik` namespace:

    ```XAML
    xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
    ```

3. Set the `IsRefreshing` property in the button click handlers and handle the `Refreshed` event:

    <snippet id='refreshview-refresh-state-programmatic' />

The following image shows the result:

![.NET MAUI RefreshView with an IsRefreshEnabled checkbox, Start Refresh and Stop Refresh buttons, and a label that shows the current IsRefreshing value](images/refreshview-refresh-state.png)

> tip For a runnable example with the RefreshView Refresh State scenario, see the [SDKBrowser Demo Application]({% slug sdkbrowser-app %}) and go to the **RefreshView > Configuration** category.

## See Also

- [Getting Started with the .NET MAUI RefreshView]({% slug refreshview-getting-started %})
- [RefreshView Events]({% slug refreshview-events %})
- [RefreshView Commands]({% slug refreshview-commands %})
