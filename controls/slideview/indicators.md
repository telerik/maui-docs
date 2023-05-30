---
title: Indicators
page_title: .NET MAUI SlideView Documentation - Indicators
description: "Learn more about the .NET MAUI SlideView indicators and their features."
position: 8
slug: slideview-indicators
---

# .NET MAUI SlideView Indicators

The `SlideViewIndicator` is a control that emphasizes changes from the current item to another item in a collection of items. This control also incorporates buttons to enable the end user to navigate between the next or previous items.

It expodes the following properties:

* `HasLooping`&mdash;Defines a value that indicates whether the navigation commands can navigate from first to last and from last to first items.

* `Orientation`&mdash;Defines the orientation of the control.

* `NavigationButtonsVisibillity`&mdash;Defines a value that controls the visibility of the navigation buttons.

* `NavigatеOnItemTap`&mdash;Defines a value indicating whether tapping on an item will update the SlideViewIndicator current index and navigation will follow.

* `AnimationDuration`(`int`)&mdash;Defines the duration in milliseconds od the animation that is run when the current index changes.

* `AnimationEasing`(`Easing`)&mdash;Defines the `Microsoft.Maui.Easing` of the animation that is run when the current index changes.

* `CurrentIndex`&mdash;Defines the index of the current item.

* `MaxVisibleItems`&mdash;Defines a value indicating the maximum number of items to be displayed.

* `ItemsSource`&mdash;Defines the SlideViewIndicator ItemsSource 
