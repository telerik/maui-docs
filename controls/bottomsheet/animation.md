---
title: Animation
page_title: .NET MAUI BottomSheet Documentation - Animation
description: Try now the Telerik BottomSheet for .NET MAUI that delivers an animation when opening/closing the bottom view.
position: 5
slug: bottomsheet-animation
---

# .NET MAUI BottomSheet Animation

Telerik .NET MAUI BottomSheet provides an option to set the animation when opening/closing the bottom view.

## Animation while opening/closing

To enable or disable the animation you need to use the `IsAnimationEnabled` (`bool`) property of `RadBottomSheet`. By default, the animation is enabled.

You can also customize the duration and easing through `AnimationDuration` and `AnimationEasing` properties.

* `AnimationDuration`(`uint`)&mdash;Defines the duration of the animation while opening/closing the bottom view. The default value is `1000`.
* `AnimationEasing`(`Microsoft.Maui.Easing`)&mdash;Specifies animation acceleration over time. The default value is `Easing.CubicOut`.

## Example

The snippet below shows how the `AnimationDuration`, `AnimationEasing` properties can be applied:



## See Also

