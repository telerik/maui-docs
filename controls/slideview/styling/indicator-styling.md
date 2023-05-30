---
title: SlideView Navigation Indicator Styling
page_title: .NET MAUI SlideView Documentation - SlideView Indicator Styling
description: Learn how to style and customize the .NET Maui SlideView Indicators.
position: 12
slug: indicators-styling
---

# .NET MAUI SlideView Indicator Styling

The SlideView exposes the `IndicatorStyle` property that allows you to adapt the style of the SlideView Indicator.

The `IndicatorStyle` property defines the custom `Microsoft.Maui.Controls.Style` that is regarded when creating the `Microsoft.Maui.Controls.Style` that will be applied to the SlideViewIndicator. To style the indicators, set the property `IndicatorStyle` to the SlideView control. You can style the indicators through the `Style` section in XAML.

The following table represents the available style properties.

|Style Property|Description|
|--------------|-----------|
| `AnimationDuration`|Defines the duration (in milliseconds) of the animation that runs when the current index changes.|
| `AnimationEasing`|Defines the `Microsoft.Maui.Easing` of the animation that runs when the current index changes.|
| `BackgroundColor`|Defines the color which will fill the background of a `VisualElement`.|
| `HeightRequest`|Defines the desired height of the element.|
| `WidthRequest`|Defines the desired width of the element.|
| `HorizontalOptions`|Defines the `LayoutOptions` that define how to lay out the element in a layout cycle.|
| `VerticalOptions`|Defines the `LayoutOptions` that define how to lay out the element in a layout cycle.|
| `IsEnabled`|Defines a value indicating whether this element is enabled in the user interface.|
| `IsVisible`|Defines a value that determines whether this element will be visible on the visual tree.|
| `MaximumHeightRequest`|Defines a value which overrides the maximum height the element will request during layout.|
| `MinimumHeightRequest`|Defines a value which overrides the minimum height the element will request during layout.|
| `MaximumWidthRequest`|Defines a value which overrides the maximum width the element will request during layout.|
| `MinimumWidthRequest`|Defines a value which overrides the mimimum width the element will request during layout.|
