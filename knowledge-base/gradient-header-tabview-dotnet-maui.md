---
title: Applying Gradient to TabView Header for .NET MAUI
description: Learn how to apply a gradient background to the Header of the TabView component in .NET MAUI.
type: how-to
page_title: Setting Gradient Background for TabView Header in .NET MAUI
slug: gradient-header-tabview-dotnet-maui
tags: tabview,.net maui, header, gradient, tabviewheaderitem
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.0 | Telerik UI for .NET MAUI TabView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I want to apply a gradient effect to the entire header of the [TabView]({%slug tabview-overview%}) component in .NET MAUI, not just individual header items. Additionally, I need transparency for the background and border properties of the header items.

This knowledge base article also answers the following questions:
- How to style TabView header with gradient in .NET MAUI?
- How to use `HeaderTemplate` for TabView in .NET MAUI?
- How to apply transparency to TabView header items in .NET MAUI?

## Solution

To achieve a gradient effect for the entire TabView header and apply transparency to the header items, follow these steps:

1. Define a `LinearGradientBrush` resource for the gradient effect.
2. Create a `ControlTemplate` for the header and use the gradient brush in its background property.
3. Set transparency for header item background and border properties using the `HeaderItemStyle`.

```xaml
<ContentPage.Resources>
    <ResourceDictionary>
        <!-- Gradient Brush for Header Background -->
        <LinearGradientBrush x:Key="brush" StartPoint="0,0" EndPoint="1,1">
            <GradientStop Color="Blue" Offset="0.0"/>
            <GradientStop Color="Blue" Offset="0.4"/>
            <GradientStop Color="Red" Offset="0.6"/>
            <GradientStop Color="Red" Offset="1.0"/>
        </LinearGradientBrush>
    
        <!-- Header Control Template -->
        <ControlTemplate x:Key="TabViewHeaderControlTemplate">
            <telerikMauiControls:RadBorder Background="{StaticResource brush}"
                                           BorderColor="{TemplateBinding BorderColor}"
                                           BorderThickness="{TemplateBinding BorderThickness}"
                                           CornerRadius="{TemplateBinding CornerRadius}"
                                           Padding="{TemplateBinding ContentPadding}"
                                           AutomationId="RadTabViewHeader">
                <ContentPresenter />
            </telerikMauiControls:RadBorder>
        </ControlTemplate>
    </ResourceDictionary>
</ContentPage.Resources>

<telerik:RadTabView x:Name="tabView" HeaderTemplate="{StaticResource TabViewHeaderControlTemplate}">
    <!-- Style for Header Items -->
    <telerik:RadTabView.HeaderItemStyle>
        <Style TargetType="telerik:TabViewHeaderItem">
            <Setter Property="FontAttributes" Value="Italic"/>
            <Setter Property="TextColor" Value="#99000000" />
            <Setter Property="Background" Value="Transparent"/>
            <Setter Property="BackgroundColor" Value="Transparent"/>
            <Setter Property="BorderColor" Value="Transparent"/>
        </Style>
    </telerik:RadTabView.HeaderItemStyle>
    
    <!-- Tab Items -->
    <telerik:TabViewItem HeaderText="Home">
        <Label Margin="10" Text="This is the content of the Home tab" />
    </telerik:TabViewItem>
    <telerik:TabViewItem HeaderText="Folder">
        <Label Margin="10" Text="This is the content of the Folder tab" />
    </telerik:TabViewItem>
    <telerik:TabViewItem HeaderText="View">
        <Label Margin="10" Text="This is the content of the View tab" />
    </telerik:TabViewItem>
</telerik:RadTabView>
```

## See Also

- [TabView Documentation]({%slug tabview-overview%})
- [Applying Gradient to TabView Header Item for .NET MAUI]({%slug gradient-header-item-tabview-dotnet-maui%})
