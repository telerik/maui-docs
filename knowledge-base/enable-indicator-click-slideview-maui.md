---
title: Enabling Indicator Click to Navigate on Items in SlideView for .NET MAUI
description: Learn how to enable the functionality to click on the indicator to navigate to items in SlideView for .NET MAUI.
type: how-to
page_title: Enable Indicator Click to Navigate to Items in SlideView for .NET MAUI
slug: enable-indicator-click-slideview-maui
tags: maui, slideview, indicator, click, swipe
res_type: kb
---

## Environment

| Property | Value |
|----------|-------|
| Product  | SlideView for .NET MAUI |
| Version  | 6.6.0 |

## Description

I want to enable the functionality to click on the indicator to navigate to items in SlideView for .NET MAUI. Currently, I am unable to click on the indicator to change the item on mobile, but it works fine on desktop.

## Solution

To enable the functionality to click on the indicator to navigate to items in SlideView for .NET MAUI, you can follow these steps:

1. In your XAML file, add the following namespace declarations:

```xml
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

2. Inside the `ContentPage` element, create a `ResourceDictionary` and define a style for the `SlideViewIndicator`:

```xml
<ContentPage.Resources>
    <ResourceDictionary>
        <Style x:Key="IndicatorStyle" TargetType="telerik:SlideViewIndicator">
            <Setter Property="NavigateOnItemTap" Value="True" />
        </Style>
    </ResourceDictionary>
</ContentPage.Resources>
```

3. Add the `IndicatorStyle` to your `RadSlideView` control and set the `NavigateOnItemTap` property to `True`:

```xml
<telerik:RadSlideView x:Name="slideview" AutomationId="slideView" IndicatorStyle="{StaticResource IndicatorStyle}">
    <!-- Add your slide view items here -->
</telerik:RadSlideView>
```

By following these steps, you will enable the functionality to click on the indicator in order to navigate to items in SlideView for .NET MAUI on mobile.

## Notes

- All indicator properties for SlideView in .NET MAUI are described in the [documentation](https://docs.telerik.com/devtools/maui/controls/slideview/indicators).

## See Also

- [SlideView Indicators Documentation](https://docs.telerik.com/devtools/maui/controls/slideview/indicators)
