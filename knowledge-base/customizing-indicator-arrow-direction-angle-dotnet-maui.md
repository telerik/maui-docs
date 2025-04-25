---
title: Customizing Indicator Arrow Direction Angle in Expander for .NET MAUI
description: Learn how to customize the indicator arrow direction and rotation angle in the RadExpander control for .NET MAUI.
type: how-to
page_title: Changing Expand Collapse Arrow Behavior in RadExpander for .NET MAUI
slug: customizing-indicator-arrow-direction-angle-dotnet-maui
tags: expander,.net maui,indicator customization,arrow direction
res_type: kb
ticketid: 1685501
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.1.0 | Telerik UI for .NET MAUI Expander | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I want to customize the expand-collapse indicator arrow in the [Expander for .NET MAUI](https://docs.telerik.com/devtools/maui/controls/expander/overview). By default, the arrow points left (`◀️`) when collapsed and down (`▼`) when expanded. My goal is to change the behavior so the arrow points down (`▼`) in the collapsed state and up (`▲`) in the expanded state.

This knowledge base article also answers the following questions:

- How to change the rotation angle of the expand-collapse arrow in Expander for .NET MAUI?
- How to customize the direction of the indicator in .NET MAUI Expander?
- How to override the default indicator behavior in Expander for .NET MAUI?

## Solution

To achieve this customization, create a custom control template for the Expander header. Below is an example of how to implement this in XAML:

1. Define the custom control template for the Expander header within a `ResourceDictionary`.
2. Replace the default arrows with custom icons or labels (`+` for collapsed and `-` for expanded).
3. Use triggers to manage the visibility or rotation of the icons based on the `IsExpanded` property.

```xaml
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
             xmlns:telerikMauiControls="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
             xmlns:expander="clr-namespace:Telerik.Maui.Controls.Expander;assembly=Telerik.Maui.Controls"
             x:Class="MauiApp3.MainPage">

    <ContentPage.Resources>
        <ResourceDictionary>
            <expander:InverseThicknessConverter x:Key="InverseThicknessConverter" />
            <expander:ExpandCollapseIndicatorLocationToGridColumnConverter x:Key="ExpandCollapseIndicatorLocationToGridColumnConverter" />
            <telerik:InvertedBooleanConverter x:Key="InvertedBooleanConverter" />

            <ControlTemplate x:Key="ExpanderHeader_ControlTemplate">
                <telerikMauiControls:RadBorder BackgroundColor="{TemplateBinding BackgroundColor}"
                                               BorderColor="{TemplateBinding BorderColor}"
                                               BorderThickness="{TemplateBinding BorderThickness}"
                                               CornerRadius="{TemplateBinding CornerRadius}"
                                               Padding="{TemplateBinding ContentPadding}"
                                               Margin="{TemplateBinding Padding, Converter={StaticResource InverseThicknessConverter}}">
                    <Grid ColumnDefinitions="Auto, *, Auto">
<telerik:RadBorder Grid.Column="{TemplateBinding IndicatorLocation, Converter={StaticResource ExpandCollapseIndicatorLocationToGridColumnConverter}}"
                                           BackgroundColor="LightBlue"
                                           WidthRequest="44"
                                           HeightRequest="44">
							<telerik:RadBorder.Triggers>
								<DataTrigger TargetType="telerik:RadBorder"
                                             Binding="{TemplateBinding IsExpanded}"
                                             Value="True">
									<Setter Property="BackgroundColor" Value="LightBlue" />
								</DataTrigger>
							</telerik:RadBorder.Triggers>
						</telerik:RadBorder>
                        <Label Text="▼"
                                TextColor="Black"
                               FontSize="Large"
                               IsVisible="{TemplateBinding IsExpanded}"
                               VerticalOptions="Center"
                               HorizontalOptions="Center"
                               Grid.Column="{TemplateBinding IndicatorLocation, Converter={StaticResource ExpandCollapseIndicatorLocationToGridColumnConverter}}"
                               Margin="0, 0, 0, 2" />
                        <Label Text="▲"
                               TextColor="Black"
                               FontSize="Large"
                               IsVisible="{TemplateBinding IsExpanded, Converter={StaticResource InvertedBooleanConverter}}"
                               VerticalOptions="Center"
                               HorizontalOptions="Center"
                               Grid.Column="{TemplateBinding IndicatorLocation, Converter={StaticResource ExpandCollapseIndicatorLocationToGridColumnConverter}}"
                               Margin="0, 0, 0, 2" />
                        <ContentPresenter Grid.Column="1" Margin="16, 0, 0, 0" />
                    </Grid>
                </telerikMauiControls:RadBorder>
            </ControlTemplate>

            <Style TargetType="telerik:ExpanderHeader">
                <Setter Property="ControlTemplate" Value="{StaticResource ExpanderHeader_ControlTemplate}" />
            </Style>
        </ResourceDictionary>
    </ContentPage.Resources>

    <telerik:RadExpander BorderColor="LightBlue" BorderThickness="2">
        <telerik:RadExpander.Header>
            <telerik:ExpanderHeader>
                <Label Text="More Options" VerticalOptions="Center" Margin="10" />
            </telerik:ExpanderHeader>
        </telerik:RadExpander.Header>
        <telerik:RadExpander.Content>
            <VerticalStackLayout Margin="10, 20, 10, 20">
                <Label Text="RadExpander for .NET MAUI is a flexible content control that helps you save screen space." HeightRequest="50" />
            </VerticalStackLayout>
        </telerik:RadExpander.Content>
    </telerik:RadExpander>
</ContentPage>
```

## Notes

Use the `Label` elements within the control template to specify the desired icons or text for the collapsed (`▼`) and expanded (`▲`) states.

## See Also

- [Expander Overview](https://docs.telerik.com/devtools/maui/controls/expander/overview)
- [Control Templates in .NET MAUI](https://learn.microsoft.com/en-us/dotnet/maui/fundamentals/controltemplate?view=net-maui-9.0)
