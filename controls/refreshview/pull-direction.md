---
title: Pull Direction
meta_title: .NET MAUI RefreshView Documentation - Pull Direction
description: Learn how to set the pull direction of the Telerik UI for .NET MAUI RefreshView to start a refresh from the top, bottom, left, or right edge.
components: ["refreshview"]
tags: .net maui, telerik .net maui, ui for .net maui, refreshview, microsoft .net maui
position: 2
slug: refreshview-pull-direction
---

# .NET MAUI RefreshView Pull Direction

The RefreshView pull direction defines the physical direction of the pull gesture and the edge at which the indicator appears. Change the pull direction when your content scrolls horizontally or when new items appear at the bottom, for example, in a chat history.

## Set the Pull Direction

To set the pull direction, use the `PullDirection` property of type `Telerik.Maui.Controls.RefreshViewPullDirection`. The property accepts the following values:

* `TopToBottom`&mdash;The user pulls from the top edge toward the bottom. This is the default value on all platforms.
* `BottomToTop`&mdash;The user pulls from the bottom edge toward the top.
* `LeftToRight`&mdash;The user pulls from the left edge toward the right.
* `RightToLeft`&mdash;The user pulls from the right edge toward the left.

> note The `LeftToRight` and `RightToLeft` values describe physical directions. The `FlowDirection` of the layout doesn't reverse them.



## Change the Pull Direction

The following example demonstrates how to change the `PullDirection` of the RefreshView.

1. Define the RefreshView in XAML:

    <snippet id='refreshview-pull-direction' />

2. Add the `telerik` namespace:

    ```XAML
    xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
    ```

3. Handle the `Refreshing` event and end the refresh when the data is loaded:

    <snippet id='refreshview-pull-direction-onrefreshing' />

The following image shows the result:

![.NET MAUI RefreshView with the refresh indicator displayed at the left edge of the content while the user pulls from left to right](images/refreshview-pull-direction.png)

> tip For a runnable example with the RefreshView Pull Direction scenario, see the [SDKBrowser Demo Application]({% slug sdkbrowser-app %}) and go to the **RefreshView > Configuration** category.

## See Also

- [Transition Mode]({% slug refreshview-transition-mode %})
- [Thresholds]({% slug refreshview-thresholds %})
- [Indicator Type]({% slug refreshview-indicator-type %})
