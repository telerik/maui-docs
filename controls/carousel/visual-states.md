---
title: Visual States
page_title: .NET MAUI Carousel Documentation - Visual States
description: Learn how to use the visual states of the Telerik UI for .NET MAUI Carousel item container to change its appearance based on its state.
components: ["carousel"]
position: 12
slug: carousel-visual-states
tags: style, visual states, item, carousel, maui, dotnet maui
---

# .NET MAUI Carousel Visual States

This article describes the visual states provided by the Carousel control.

You can use these visual states to change the appearance of the item containers (`RadCarouselItemView`) based on their state&mdash;such as when an item is highlighted, hovered, pressed, disabled, and more.

The Carousel provides the following `CommonStates` visual states:

| Visual State | Description |
| ------------- | --------------- |
| `Normal` | Applies to items two or more positions from the highlighted item. |
| `MouseOver` | Applies when the mouse cursor is hovering over an item two or more positions from the highlighted item. |
| `Pressed` | Applies when an item two or more positions from the highlighted item is pressed. |
| `Highlighted` | Applies to the highlighted item. |
| `HighlightedMouseOver` | Applies when the mouse cursor is hovering over the highlighted item. |
| `HighlightedPressed` | Applies when the highlighted item is pressed. |
| `Previous` | Applies to the item before the highlighted item. |
| `PreviousMouseOver` | Applies when the mouse cursor is hovering over the item before the highlighted item. |
| `PreviousPressed` | Applies when the item before the highlighted item is pressed. |
| `Next` | Applies to the item after the highlighted item. |
| `NextMouseOver` | Applies when the mouse cursor is hovering over the item after the highlighted item. |
| `NextPressed` | Applies when the item after the highlighted item is pressed. |
| `Disabled` | Applies when the item container `IsEnabled` is `False`. |

For an example of targeting these visual states in an `ItemViewStyle`, see the [Carousel Styling]({%slug carousel-styling%}) article.

## See Also

- [Styling]({%slug carousel-styling%})
- [Highlighted Item]({%slug carousel-highlighted-item%})
- [Item Effects]({%slug carousel-item-effects%})
