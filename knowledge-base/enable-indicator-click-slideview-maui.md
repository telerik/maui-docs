---
title: Enabling Navigation between SlideView Items by Using the Indicator
description: Learn how to enable the SlideView for .NET MAUI to navigate between the items when users click on the indicator on their mobile devices.
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

I want to enable users to navigate to the different SlideView items by using the indicator. Currently, changing the item with the indicator works fine on desktop, but isn't possible on mobile devices.

## Solution

To enable navigation through the indicator in SlideView for .NET MAUI, follow these steps:

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

By following these steps, you enable mobile device users to switch between SlideView items by tapping the indicator.

## Notes

For all available SlideView indicator properties, see the [.NET MAUI SlideView Indicator](https://docs.telerik.com/devtools/maui/controls/slideview/indicators) article.

## See Also

- [SlideView Indicators Documentation](https://docs.telerik.com/devtools/maui/controls/slideview/indicators)
