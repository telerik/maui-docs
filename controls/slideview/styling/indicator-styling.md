---
title: SlideView Navigation Indicator Styling
page_title: .NET MAUI SlideView Documentation - SlideView Indicator Styling
description: "Learn how to style and customize the .NET Maui SlideView Indicators."
position: 12
slug: indicators-styling
---

# .NET MAUI SlideView Indicator Styling

The SlideView exposes a property about the Indicators Styling:

* `IndicatorStyle`&mdash;Defines the custom `Microsoft.Maui.Controls.Style` that is taken into account when creating the actual `Microsoft.Maui.Controls.Style` that will be applied to the SlideViewIndicator.

The property must be set to the SlideView control if need to style the indicators. The indicators could be styled throught the Style section in XAML.

Here are the properties that could be styled:

* `AnimationDuration`&mdash;Defines the duration in milliseconds od the animation that is run when the current index changes.

* `AnimationEasing`&mdash;Defines the `Microsoft.Maui.Easing` of the animation that is run when the current index changes.

* `BackgroundColor`&mdash;Defines the color which will fill the background of a VisualElement.T

* `HeightRequest`&mdash;Defines the desired height of the element

* `WidthRequest`&mdash;Defines the desired width of the element.

* `HorizontalOptions`&mdash;Defines the LayoutOptions that define how the element gets laid in a layout cycle.

* `VerticalOptions`&mdash;Defines the LayoutOptions that define how the element
gets laid in a layout cycle

* `IsEnabled`&mdash;Defines a value indicating whether this element is enabled in the user interface.

* `IsVisible`&mdash;Defines a value that determines whether this element will be visible on the visual tree.

* `MaximumHeightRequest`&mdash;Defines a value which overrides the maximum height the element will request during layout.

* `MinimumHeightRequest`&mdash;Defines a value which overrides the minimum height the element will request during layout.

* `MaximumWidthRequest`&mdash;Defines a value which overrides the maximum width the element will request during layout.

* `MinimumWidthRequest`&mdash;Defines a value which overrides the mimimum width the element will request during layout.