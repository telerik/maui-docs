---
title: Item Effects
meta_title: .NET MAUI Carousel Documentation - Item Effects
description: Learn how to configure the scale and opacity effects that the Telerik UI for .NET MAUI Carousel applies to items based on their position.
tags: .net maui, telerik .net maui, ui for .net maui, carousel, item effects, scale, opacity
position: 7
slug: carousel-item-effects
---

# .NET MAUI Carousel Item Effects

The Carousel item effects change the scale and opacity of the items based on their position relative to the viewport center. The effects make the highlighted item stand out and give the neighboring items a receding look. While the user scrolls, the Carousel interpolates the values smoothly between positions.

## Enable and Configure the Item Effects

To control the item effects, use the following properties of the `RadCarousel`:

* `AreItemEffectsEnabled` (`bool`)&mdash;Specifies whether the Carousel applies effects to the items. The default value is `true`.
* `ItemEffectSettings` (`Telerik.Maui.Controls.Carousel.CarouselItemEffectSettings`)&mdash;Specifies the effects for each item position. The value cannot be `null`.

The `CarouselItemEffectSettings` class exposes the following properties of type `CarouselItemEffect`:

* `Highlighted`&mdash;Defines the effect for the item at the center of the viewport. By default, the scale and opacity are both `1`.
* `Previous`&mdash;Defines the effect for the item one position before the center. By default, the scale is `0.8` and the opacity is `0.6`.
* `Next`&mdash;Defines the effect for the item one position after the center. By default, the scale is `0.8` and the opacity is `0.6`.
* `Normal`&mdash;Defines the effect for the items two or more positions from the center. By default, the scale is `0.8` and the opacity is `0.6`.

Each `CarouselItemEffect` exposes the following properties:

* `Scale` (`double`)&mdash;Specifies the item scale, between `0` and `1`. The default value is `1`.
* `Opacity` (`double`)&mdash;Specifies the item opacity, between `0` and `1`. The default value is `1`.

## Apply Custom Scale and Opacity Effects

The following example sets a different scale and opacity for each item position.

1. Define the Carousel in XAML:

    <snippet id='carousel-item-effects' />

1. Add the `telerik` namespace:

    ```XAML
    xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
    ```

1. Add the business object:

    <snippet id='carousel-item-model' />

1. Define the `ViewModel`:

    <snippet id='carousel-viewmodel' />

As a result, the highlighted item is displayed at full size, the adjacent items are slightly smaller and semi-transparent, and the farther items are smaller and fainter.

> tip For a runnable example with the Carousel Item Effects scenario, see the [SDKBrowser Demo Application]({% slug sdkbrowser-app %}) and go to the **Carousel > Features** category.

## See Also

- [Item Size and Spacing]({% slug carousel-item-size-and-spacing %})
- [Styling]({% slug carousel-styling %})
