---
title: Commands
meta_title: .NET MAUI Carousel Documentation - Commands
description: Learn how to use the navigation commands of the Telerik UI for .NET MAUI Carousel to move to the previous or next item from buttons.
tags: .net maui, telerik .net maui, ui for .net maui, carousel, commands, navigation
position: 8
slug: carousel-commands
---

# .NET MAUI Carousel Commands

The Carousel exposes navigation commands that move the highlighted item to the previous or next item. Bind these commands to buttons when you want to provide navigation in addition to swiping, for example, on desktop platforms.

## Navigation Commands and Properties

The Carousel exposes the following read-only commands:

* `NavigatePreviousCommand` (`ICommand`)&mdash;Navigates to the previous item.
* `NavigateNextCommand` (`ICommand`)&mdash;Navigates to the next item.

To allow or prevent navigation in a direction, use the following properties:

* `AllowPrevious` (`bool`)&mdash;Specifies whether the Carousel allows navigation to the previous item. The default value is `true`.
* `AllowNext` (`bool`)&mdash;Specifies whether the Carousel allows navigation to the next item. The default value is `true`.

## Navigate with Previous and Next Buttons

The following example binds two buttons to the navigation commands of the Carousel and uses checkboxes to toggle the `AllowPrevious` and `AllowNext` properties.

1. Define the Carousel and the buttons in XAML:

    <snippet id='carousel-navigation-commands' />

1. Add the `telerik` namespace:

    ```XAML
    xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
    ```

1. Define the business object:

    <snippet id='carousel-item-model' />

1. Define the `ViewModel`:

    <snippet id='carousel-viewmodel' />

This is the result:

![.NET MAUI Carousel with two buttons that navigate to the previous and next items](images/carousel-commands.gif)

> tip For a runnable example demonstrating the Carousel commands, see the [SDKBrowser Demo Application]({% slug sdkbrowser-app %}) and go to the **Carousel > Commands** category.

## See Also

- [Highlighted Item]({% slug carousel-highlighted-item %})
- [Carousel Events]({% slug carousel-events %})
- [Styling]({% slug carousel-styling %})
