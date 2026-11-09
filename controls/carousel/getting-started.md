---
title: Getting Started
meta_title: .NET MAUI Carousel Documentation - Getting Started
description: Learn how to add the Telerik UI for .NET MAUI Carousel to a page, bind it to a collection of items, and define the template of the items.
tags: carousel for .net maui, .net maui, ui for .net maui, getting started
position: 2
slug: carousel-getting-started
---

# Getting Started with the .NET MAUI Carousel

This guide provides the information you need to start using the Telerik UI for [.NET MAUI Carousel]({% slug carousel-overview %}) by adding the control to your project.

At the end, the Carousel displays a horizontal sequence of image items, where the highlighted item is at the center and parts of the previous and next items are visible on both sides.

## Prerequisites

Before adding the Carousel, complete the following steps:

1. [Set up your .NET MAUI application]({%slug maui-quick-start %}#prerequisites).

1. [Set Up Telerik Development Environment]({%slug maui-quick-start %}#set-up-telerik-development-environment)

## Define the Carousel

The Carousel displays the items from its `ItemsSource` collection and uses the `ItemTemplate` to define how each item looks. Items in the collection must not be `null`.

To display the Carousel on a page, complete the following steps:

1. Define a business object that describes each item:

    <snippet id='carousel-item-model' />

1. Define a view model that exposes the collection of items:

    <snippet id='carousel-viewmodel' />

1. Add the Carousel to your page:

    <snippet id='carousel-getting-started-xaml' />
    <snippet id='carousel-getting-started-csharp' />

1. Add the `telerik` namespace:

    ```XAML
    xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
    ```

1. Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `CreateMauiApp` method of the `MauiProgram.cs` file of your project:

    ```C#
    using Telerik.Maui.Controls.Compatibility;

    public static class MauiProgram
    {
        public static MauiApp CreateMauiApp()
        {
            var builder = MauiApp.CreateBuilder();
            builder
                .UseTelerik()
                .UseMauiApp<App>()
                .ConfigureFonts(fonts =>
                {
                    fonts.AddFont("OpenSans-Regular.ttf", "OpenSansRegular");
                });
            return builder.Build();
        }
    }
    ```

When you run the app, the first item is highlighted at the center of the Carousel. Swipe or scroll to move to the other items.

> tip For a runnable example with the Carousel Getting Started scenario, see the [SDKBrowser Demo Application]({% slug sdkbrowser-app %}) and go to the **Carousel > Getting Started** category.

## Additional Resources

- [.NET MAUI Carousel Forum Page](https://www.telerik.com/forums/maui)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Highlighted Item]({% slug carousel-highlighted-item %})
- [Item Size and Spacing]({% slug carousel-item-size-and-spacing %})
- [Styling]({% slug carousel-styling %})
