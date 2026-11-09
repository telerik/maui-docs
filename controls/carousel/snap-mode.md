---
title: Snap Mode
meta_title: .NET MAUI Carousel Documentation - Snap Mode
description: Learn how to use the SnapMode property of the Telerik UI for .NET MAUI Carousel to scroll by one item or through multiple items per swipe.
tags: .net maui, telerik .net maui, ui for .net maui, carousel, snap mode
position: 6
slug: carousel-snap-mode
---

# .NET MAUI Carousel Snap Mode

The Carousel snap mode defines how many items the user can scroll through during a single interaction. After each interaction, the Carousel snaps an item into the highlighted position.

## Set the Snap Mode

To set the snap mode, use the `SnapMode` (`enum` of type `Telerik.Maui.Controls.Carousel.CarouselSnapMode`) property. The available values are:

* `Single`&mdash;The Carousel scrolls by one item per user interaction. Use this value when users review items one by one, for example, in onboarding flows.
* `Multiple`&mdash;The Carousel scrolls through multiple items per user interaction, depending on the swipe speed. This is the default value.

## Scroll by One Item per Swipe

The following example demonstrates how to change the `SnapMode` of the Carousel.

1. Define the Carousel in XAML:

    <snippet id='carousel-snap-mode' />

1. Add the `telerik` namespace:

    ```XAML
    xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
    ```

1. Add the business object:

    <snippet id='carousel-item-model' />

1. Define the `ViewModel`:

    <snippet id='carousel-viewmodel' />

> tip For a runnable example with the Carousel Snap Mode scenario, see the [SDKBrowser Demo Application]({% slug sdkbrowser-app %}) and go to the **Carousel > Features** category.

## See Also

- [Orientation]({% slug carousel-orientation %})
- [Carousel Commands]({% slug carousel-commands %})
