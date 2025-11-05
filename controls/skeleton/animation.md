---
title: Animation
meta_title: .NET MAUI Skeleton Documentation - Animation
description: Learn what are the animation types you can apply to the Telerik .NET MAUI Skeleton control when the content is loading.
position: 2
tags: .net maui, telerik .net maui, ui for .net maui, shimmer, microsoft .net maui
slug: skeleton-animation
---

# .NET MAUI Skeleton Animation

The Skeleton control includes built-in animation options that allow you to create a smooth and engaging loading experience for the app users.

You can change the animation type by setting the `AnimationType` (`enum` of type `Telerik.Maui.Controls.Skeleton.SkeletonAnimationType`) property to one of the available options:

* `None`&mdash;No animation is applied to the Skeleton control. The skeleton remains static without any visual effects.
* (Default) `Pulse`&mdash;Applies a pulsing animation that smoothly fades the skeleton in and out, creating a subtle breathing effect. This is the default animation type and provides visual feedback that content is actively loading.

![Telerik UI for .NET MAUI Skeleton Animation Types](images/skeleton-animation-types.gif)

Check below a quick example on how to set the `AnimationType` property to `None`:

<snippet id='skeleton-animation-type' />

> For a runnable example with the Skeleton Animation, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **Skeleton > Animation** category.

## See Also

- [Built-in Views]({%slug skeleton-default-view%})
- [Configuration]({%slug skeleton-configuration%})
- [Custom Views]({%slug skeleton-custom-view%})
- [Styling]({%slug skeleton-styling%})
