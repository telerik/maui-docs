---
title: Item Size and Spacing
meta_title: .NET MAUI Carousel Documentation - Item Size and Spacing
description: Learn how to set the peek area ratio and the item spacing of the Telerik UI for .NET MAUI Carousel to control how neighboring items are displayed.
tags: .net maui, telerik .net maui, ui for .net maui, carousel, peek area, spacing
position: 4
slug: carousel-item-size-and-spacing
---

# .NET MAUI Carousel Item Size and Spacing

The Carousel item size depends on the part of the viewport left for the neighboring items. Adjust this part and the spacing between items to show more or less of the previous and next items.

## Set the Peek Area and Spacing

To configure the size of the items and the space between them, use the following properties:

* `PeekAreaRatio` (`double`)&mdash;Specifies the portion of the viewport left for the neighboring items on both sides of the highlighted item. Valid values range from `0.0` to `0.9`. At `0.0`, the highlighted item fills the viewport. At `0.9`, the highlighted item takes 10% of the viewport. The default value is `0.4`.
* `ItemSpacing` (`double`)&mdash;Specifies the spacing between adjacent items in device-independent units. The value must be finite and nonnegative. The default value is `16`.

When `PeekAreaRatio` is `0`, the Carousel ignores `ItemSpacing`. When [item effects]({% slug carousel-item-effects %}) are enabled, the Carousel keeps the spacing between the scaled items.

## Example of Custom Peek Area and Spacing

The following example sets custom `PeekAreaRatio` and `ItemSpacing` values.

1. Define the Carousel in XAML:

    <snippet id='carousel-item-size-and-spacing' />

1. Add the `telerik` namespace:

    ```XAML
    xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
    ```

1. Add the business object:

    <snippet id='carousel-item-model' />

1. Define the `ViewModel`:

    <snippet id='carousel-viewmodel' />

> tip For a runnable example with the Carousel Item Size and Spacing scenario, see the [SDKBrowser Demo Application]({% slug sdkbrowser-app %}) and go to the **Carousel > Features** category.

## See Also

- [Item Effects]({% slug carousel-item-effects %})
- [Orientation]({% slug carousel-orientation %})
- [Styling]({% slug carousel-styling %})
