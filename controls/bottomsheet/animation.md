---
title: Animation
page_title: .NET MAUI BottomSheet Documentation - Animation
description: Learn how to configure animation settings for the Telerik BottomSheet for .NET MAUI, including duration, easing, and enable/disable options.
position: 5
slug: bottomsheet-animation
---

# .NET MAUI BottomSheet Animation

Adding an animation to the BottomSheet provides visual continuity and makes the interface feel more responsive and polished. The Telerik .NET MAUI BottomSheet provides an option to set the animation when opening/closing the bottom view.

## Animation while Opening/Closing

To enable or disable the animation, use the `IsAnimationEnabled` (`bool`) property of `RadBottomSheet`. By default, the animation is enabled.

You can also customize the animation's duration and easing through the `AnimationDuration` and `AnimationEasing` properties.

* `AnimationDuration`(`uint`)&mdash;Defines the duration of the animation while opening/closing the bottom view. The default value is `1000` milliseconds.
* `AnimationEasing`(`Microsoft.Maui.Easing`)&mdash;Specifies animation acceleration over time. The default value is `Easing.CubicOut`.

> For a runnable example with the BottomSheet Animation scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **BottomSheet > Features** category.

## See Also

- [Configure the BottomSheet]({%slug bottomsheet-configuration%})
- [Style the BottomSheet]({%slug bottomsheet-styling%})
- [Events]({%slug bottomsheet-events%})
- [Methods]({%slug bottomsheet-methods%})