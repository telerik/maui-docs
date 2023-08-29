---
title: SlideView Navigation Indicator Styling
page_title: .NET MAUI SlideView Documentation - SlideView Indicator Styling
description: Learn how to style and customize the .NET Maui SlideView Indicators.
position: 12
slug: indicators-styling
---

# .NET MAUI SlideView Indicator Styling

The SlideView exposes the `IndicatorStyle` property that allows you to adapt the style of the SlideView Indicator.

The `IndicatorStyle`(Style with target type `telerik:SlideViewIndicator`) property defines the custom style that is regarded when creating the `Microsoft.Maui.Controls.Style` that will be applied to the SlideViewIndicator. To style the indicators, set the property `IndicatorStyle` to the SlideView control. You can style the indicators through the `Style` section in XAML.

The following table represents the available style properties.

|Style Property|Description|
|--------------|-----------|
| `AnimationDuration`(`int`)|Defines the duration (in milliseconds) of the animation that runs when the current index changes.|
| `AnimationEasing`(`Easing`)|Defines the `Microsoft.Maui.Easing` of the animation that runs when the current index changes.|
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

Further customize the indicator by using the `SlideViewIndicatorItem`. The customization is shown in the example below.

## Example

**1.** Add SlideView definition in XAML:

<snippet id='slideview-indicator-styling' />

**2.** Add Style resource for the `SlideViewIndicator`:

<snippet id='slideview-indicator-styling-resource' />

**3.** Add Style resource for the `SlideViewIndicatorItem`:

<snippet id='slideview-indicator-item-custom-template' />

See the result below:

![.NET MAUI SlideView Indicator Styling](images/slideview-indicator-styling.gif)

> For a runnable example with the SlideView Indicator Styling scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **SlideView > Styling**.

## See Also

- [Binding SlideView to Data]({%slug slideview-data-binding%})
- [Using Navigation Buttons in SlideView]({%slug slideview-interaction%})
- [Executing Commands on Slide Action]({%slug slideview-commands%})
- [Handling the SlideView Events]({%slug slideview-events%})
- [Using an Item Template in SlideView]({%slug slideview-item-template%})
- [Changing the SlideView Appearance through a Control Template]({%slug slideview-control-template%})
