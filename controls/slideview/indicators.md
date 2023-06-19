---
title: Indicator
page_title: .NET MAUI SlideView Documentation - Indicator
description: Learn more about the .NET MAUI SlideView indicators and their features.
position: 6
slug: slideview-indicators
---

# .NET MAUI SlideView Indicator

The SlideViewIndicator is a control that emphasizes changes from the current item to another item in a collection of items. This control also incorporates buttons to enable the end user navigate between the next or previous items.

The following table represents the properties of the SlideViewIndicator.

|Property| Description|
|--------|------------|
| `HasLooping`|Defines a value that indicates whether the navigation commands can navigate from the first to the last and from the last to the first items.|
| `Orientation`|Defines the orientation of the control.|
| `NavigationButtonsVisibillity`|Defines a value that controls the visibility of the navigation buttons.|
| `NavigatеOnItemTap`|Defines a value indicating whether tapping on an item will update the current index of the SlideViewIndicator and whether navigation will follow.|
| `AnimationDuration`(`int`)|Defines the duration (in milliseconds) of the animation that runs when the current index changes.|
| `AnimationEasing`(`Easing`)|Defines the `Microsoft.Maui.Easing` of the animation that runs when the current index changes.|
| `CurrentIndex`|Defines the index of the current item.|
| `MaxVisibleItems`|Defines a value indicating the maximum number of items to be displayed.|
| `ItemsSource`|Defines the `ItemsSource` of the SlideViewIndicator.|

## See Also

- [Styling the SlideView Indicators]({%slug indicators-styling%})