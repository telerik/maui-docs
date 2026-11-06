---
title: Orientation
meta_title: .NET MAUI Carousel Documentation - Orientation
description: Learn how to arrange the items of the Telerik UI for .NET MAUI Carousel horizontally or vertically by setting the Orientation property.
tags: .net maui, telerik .net maui, ui for .net maui, carousel, orientation
position: 5
slug: carousel-orientation
---

# .NET MAUI Carousel Orientation

The Carousel orientation defines the direction in which the items are arranged and scrolled. Use a vertical orientation for layouts such as feeds or tall cards, and the horizontal orientation for galleries and banners.

## Set the Orientation

To set the direction of the items, use the `Orientation` (`Telerik.Maui.Orientation`) property. The available values are:

* `Horizontal`&mdash;The items are arranged and scrolled from left to right. This is the default value.
* `Vertical`&mdash;The items are arranged and scrolled from top to bottom.

## Display a Vertical Carousel

The following example sets the `Orientation` of the Carousel to `Vertical`.

1. Define the Carousel in XAML:

    <snippet id='carousel-orientation' />

1. Add the `telerik` namespace:

    ```XAML
    xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
    ```

1. Add the business object:

    <snippet id='carousel-item-model' />

1. Define the `ViewModel`:

    <snippet id='carousel-viewmodel' />

> tip For a runnable example with the Carousel Orientation scenario, see the [SDKBrowser Demo Application]({% slug sdkbrowser-app %}) and go to the **Carousel > Features** category.

## See Also

- [Item Size and Spacing]({% slug carousel-item-size-and-spacing %})
- [Snap Mode]({% slug carousel-snap-mode %})
