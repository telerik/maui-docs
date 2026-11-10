---
title: Thresholds
meta_title: .NET MAUI RefreshView Documentation - Thresholds
description: Learn how to set the pull distances at which the indicator appears and a refresh starts in the Telerik UI for .NET MAUI RefreshView control.
components: ["refreshview"]
tags: .net maui, telerik .net maui, ui for .net maui, refreshview, microsoft .net maui
position: 6
slug: refreshview-thresholds
---

# .NET MAUI RefreshView Thresholds

The RefreshView thresholds define how far the user must pull the content before the indicator appears and before a refresh starts. Adjust the thresholds to prevent accidental refreshes or to make the gesture shorter on small screens.

## Configure the Pull Distances

To configure the pull distances and the indicator size, use the following properties. All values are in device-independent .NET MAUI units:

* `IndicatorThreshold` (`double`)&mdash;Specifies the pull distance at which the indicator starts to appear. The default value is `0`. If the value isn't less than `PullingThreshold`, the indicator appears just before the pulling threshold is reached.
* `PullingThreshold` (`double`)&mdash;Specifies the pull distance required to start a refresh when the user releases the gesture. The default value is `80`. The value must be greater than `0`.
* `IndicatorLength` (`double`)&mdash;Specifies the length of the refresh indicator along the pull direction. The default value is `48`. The value must be greater than `0`.

The RefreshView also exposes the read-only `Progress` (`double`) property. `Progress` returns the normalized pull progress from `0.0` to `1.0`. The value is `1.0` while a refresh is in progress.

## Set Custom Thresholds

The following example demonstrates how to set the `IndicatorThreshold`, `PullingThreshold`, and `IndicatorLength` properties of the RefreshView.

1. Define the RefreshView in XAML:

    <snippet id='refreshview-thresholds' />

2. Add the `telerik` namespace:

    ```XAML
    xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
    ```

3. Handle the `Refreshing` event and end the refresh when the data is loaded:

    <snippet id='refreshview-thresholds-onrefreshing' />

> tip For a runnable example with the RefreshView Thresholds scenario, see the [SDKBrowser Demo Application]({% slug sdkbrowser-app %}) and go to the **RefreshView > Configuration** category.

## See Also

- [Pull Direction]({% slug refreshview-pull-direction %})
- [Transition Mode]({% slug refreshview-transition-mode %})
- [RefreshView Events]({% slug refreshview-events %})
