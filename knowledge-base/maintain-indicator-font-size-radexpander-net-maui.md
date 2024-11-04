---
title: Maintaining the Indicator Font Size Scale in RadExpander for .NET MAUI
description: Learn how to stop the font auto scaling of the indicator in RadExpander for .NET MAUI.
type: how-to
page_title: How to disable the auto scaling of the Indicator in RadExpander for .NET MAUI
slug: maintain-indicator-font-size-radexpander-net-maui
tags: radexpander, .net maui, indicator font size
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | --- | ---- |
| 6.8.0 | Telerik UI for .NET MAUI Expander | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)|

## Description

I want to maintain the indicator font size in RadExpander for .NET MAUI. However, I don't see a way to set `FontAutoScalingEnabled="False"` for the indicator. Is it possible to achieve this?

## Solution

To maintain the indicator font size in RadExpander for .NET MAUI, you can use an implicit style and set the `FontAutoScalingEnabled` property. 

**1.** Add the necessary namespaces to your XAML file:

```xml
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
xmlns:expander="clr-namespace:Telerik.Maui.Controls.Expander;assembly=Telerik.Maui.Controls"
```

**2.** Define an implicit style for the `ExpandCollapseIndicator` control:

```xml
<ContentPage.Resources>
    <ResourceDictionary>
        <Style TargetType="expander:ExpandCollapseIndicator">
            <Setter Property="FontAutoScalingEnabled" Value="False"/>
        </Style>
    </ResourceDictionary>
</ContentPage.Resources>
```

**3.** Use the `RadExpander` control with the desired indicator font settings:

```xml
<telerik:RadExpander x:Name="expander"
                     BorderColor="LightBlue"
                     BorderThickness="2">
    <telerik:RadExpander.Header>
        <telerik:ExpanderHeader IndicatorText="&#x203A;"
                                IndicatorColor="Blue"
                                IndicatorFontFamily="Arial"
                                IndicatorFontSize="16"
                                IndicatorLocation="End"
                                IndicatorAnimationDuration="1000"
                                BorderColor="LightBlue"
                                BorderThickness="2">
            <Label Text="More Options"
                   VerticalOptions="Center"
                   Margin="10" />
        </telerik:ExpanderHeader>
    </telerik:RadExpander.Header>
    <telerik:RadExpander.Content>
        <VerticalStackLayout Margin="10, 20, 10, 20">
            <Label Text="RadExpander for .NET MAUI is a flexible content control that helps you save screen space." HeightRequest="50" />
        </VerticalStackLayout>
    </telerik:RadExpander.Content>
</telerik:RadExpander>
```
