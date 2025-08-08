---
title: Animation
page_title: .NET MAUI BottomSheet Documentation - Animation
description: Learn how to configure animation settings for the Telerik BottomSheet for .NET MAUI, including duration, easing, and enable/disable options.
position: 5
slug: bottomsheet-animation
---

# .NET MAUI BottomSheet Animation

Adding animation to the BottomSheet provides visual continuity and makes the interface feel more responsive and polished. Smooth transitions help users understand the relationship between different states and create a more engaging user experience.

The Telerik .NET MAUI BottomSheet provides comprehensive animation options for opening, closing, and state transitions, whether triggered programmatically or through user interactions like swipe gestures.

The following properties control the animation behavior of the BottomSheet:

To enable or disable the animation, use the `IsAnimationEnabled` (`bool`) property of `RadBottomSheet`. By default, the animation is enabled.

You can also customize the animation's duration and easing by using the following properties.

* `AnimationDuration`(`uint`)&mdash;Defines the duration of the animation while opening/closing the bottom view. The default value is `1000` milliseconds.
* `AnimationEasing`(`Microsoft.Maui.Easing`)&mdash;Specifies animation acceleration over time. The default value is `Easing.CubicOut`.

> For a runnable example with the BottomSheet Animation scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **BottomSheet > Features** category.

## See Also

- [Swipe Gesture]({%slug bottomsheet-swipe-gesture%})
- [Configure the BottomSheet]({%slug bottomsheet-configuration%})
- [Style the BottomSheet]({%slug bottomsheet-styling%})
- [Events]({%slug bottomsheet-events%})
- [Methods]({%slug bottomsheet-methods%})