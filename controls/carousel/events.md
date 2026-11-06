---
title: Events
meta_title: .NET MAUI Carousel Documentation - Events
description: Learn how to handle the HighlightedItemChanged and Scrolled events of the Telerik UI for .NET MAUI Carousel to respond to user actions.
tags: .net maui, telerik .net maui, ui for .net maui, carousel, events
position: 9
slug: carousel-events
---

# .NET MAUI Carousel Events

The Telerik UI for .NET MAUI Carousel raises events when the highlighted item changes and when the scroll position changes. Handle these events to update other parts of the UI or to run custom logic.

The Carousel exposes the following events:

* `HighlightedItemChanged` event &mdash; Occurswhen the highlighted item changes. The event handler receives the following parameters:
    * The `sender` argument, which is of type `object`, but can be cast to the `RadCarousel` type.
    * A `CarouselHighlightedItemChangedEventArgs` object, which provides the following properties:
        * `OldHighlightedItem` (`object`)&mdash;Gets the item that was highlighted before the change.
        * `NewHighlightedItem` (`object`)&mdash;Gets the item highlighted after the change.
        * `OldHighlightedIndex` (`int`)&mdash;Gets the zero-based index highlighted before the change, or `-1` if no item was highlighted.
        * `NewHighlightedIndex` (`int`)&mdash;Gets the zero-based index highlighted after the change, or `-1` if no item is highlighted.

* `Scrolled` event &mdash; Occurs when its scroll position changes. The event handler receives the following parameters:
    * The `sender` argument, which is of type `object`, but can be cast to the `RadCarousel` type.
    * A `CarouselScrolledEventArgs` object, which provides the following properties:
        * `ScrollOffset` (`double`)&mdash;Gets the scroll offset along the Carousel orientation, in device-independent units.
        * `ItemPosition` (`double`)&mdash;Gets the zero-based position of the viewport center between item centers. Values outside the item range are possible during overscroll.

## Handle the Carousel Events

The following example subscribes to the `HighlightedItemChanged` and `Scrolled` events.

1. Define the Carousel in XAML:

    <snippet id='carousel-events' />

1. Add the `telerik` namespace:

    ```XAML
    xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
    ```

1. Define the event handlers:

    <snippet id='carousel-events-handlers' />

1. Add the business object:

    <snippet id='carousel-item-model' />

1. Define the `ViewModel`:

    <snippet id='carousel-viewmodel' />

> tip For a runnable example demonstrating the Carousel events, see the [SDKBrowser Demo Application]({% slug sdkbrowser-app %}) and go to the **Carousel > Events** category.

## See Also

- [Highlighted Item]({% slug carousel-highlighted-item %})
- [Carousel Commands]({% slug carousel-commands %})
