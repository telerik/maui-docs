---
title: Transition Mode
meta_title: .NET MAUI RefreshView Documentation - Transition Mode
description: Learn how to set the transition mode of the Telerik UI for .NET MAUI RefreshView to push, slide over, or reveal the indicator while pulling.
components: ["refreshview"]
tags: .net maui, telerik .net maui, ui for .net maui, refreshview, microsoft .net maui
position: 5
slug: refreshview-transition-mode
---

# .NET MAUI RefreshView Transition Mode

The RefreshView transition mode defines how the indicator and the content move while the user pulls. Choose a transition mode to match the native pull-to-refresh behavior of a platform or to keep the same behavior on all platforms.

## Select the Transition Mode

To select the transition mode, set the `TransitionMode` property of type `Telerik.Maui.Controls.RefreshView.RefreshViewTransitionMode`. The property accepts the following values:

* `Push`&mdash;Moves the content with the pull while the indicator slides in from the selected edge. Default on Windows.
* `Slide`&mdash;Slides the indicator over the content. The content doesn't move. Default on Android.
* `Reveal`&mdash;Keeps the indicator at the selected edge and progressively reveals the indicator as the content moves with the pull. Default on iOS and MacCatalyst.

The selected edge is defined by the [Pull Direction]({% slug refreshview-pull-direction %}) of the RefreshView.

## Set the Transition Mode

The following example demonstrates how to set the `TransitionMode` property of the RefreshView.

1. Define the RefreshView in XAML:

    <snippet id='refreshview-transition-mode' />

2. Add the `telerik` namespace:

    ```XAML
    xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
    ```

3. Handle the `Refreshing` event and end the refresh when the data is loaded:

    <snippet id='refreshview-transition-mode-onrefreshing' />

> tip For a runnable example with the RefreshView Transition Mode scenario, see the [SDKBrowser Demo Application]({% slug sdkbrowser-app %}) and go to the **RefreshView > Configuration** category.

## See Also

- [Pull Direction]({% slug refreshview-pull-direction %})
- [Thresholds]({% slug refreshview-thresholds %})
- [Indicator Type]({% slug refreshview-indicator-type %})
