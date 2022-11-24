---
title: Animations
page_title: .NET MAUI Popup Documentation - Animations
description: "Set the animation when the user opens or closes the Telerik UI for .NET MAUI Popup and customize its duration and acceleration."
position: 6
slug: popup-animations
---

# .NET MAUI Popup Animations

The Popup provides two built-in animations that are played when the Popup is shown or hidden.

You can apply the desired animation through the `AnimationType` property which exposes the following options:

* (Disables the animation) `None`
* (Default) `Fade`
* `Zoom`

You can also customize the duration and acceleration over time (easing) through the following properties:

* `AnimationDuration`&mdash;Set in ms. Defaults to 300ms.
* `AnimationEasing` (of type `Microsoft.Maui.Easing`)&mdash;Defaults to `Easing.Linear`.

## See Also

- [Getting Started with Telerik UI for .NET MAUI Popup]({% slug popup-getting-started %})
