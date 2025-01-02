---
title: Customizing RadioButtonToolbarItem Style in .NET MAUI Toolbar
description: Learn how to change the style of RadioButtonToolbarItems in a .NET MAUI Toolbar, including background color and text color, when selected.
type: how-to
page_title: How to Customize RadioButtonToolbarItem Style in a .NET MAUI Toolbar Using Visual State Manager
slug: customize-radiobuttontoolbaritem-style-dotnet-maui
tags: visualstatemanager, radiobuttontoolbaritem, style, .net maui, toolbar
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 9.0.0 | Telerik UI for .NET MAUI Toolbar | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

When using RadioButtonToolbarItems in a Toolbar, there may be a need to customize their style beyond the default settings when they are selected. This includes changing properties such as background color and text color.

 This knowledge base article also answers the following questions:
- How to apply custom styles to RadioButtonToolbarItems in .NET MAUI?
- How to use `VisualStateManager` to change the style of Toolbar items upon selection?
- How to set different visual states for RadioButtonToolbarItems in a .NET MAUI Toolbar?

## Solution

To customize the style of RadioButtonToolbarItems when selected, leverage the `VisualStateManager` (VSM). You need to declare all visual states, including `Normal`, `PointerOver`, `Selected`, `Disabled`, etc., for the RadioButtonToolbarItem.

Here is an example demonstrating how to use the `VisualStateManager` to customize the appearance of RadioButtonToolbarItems:

```xaml
<ContentView.Resources>
    <Style x:Key="RadioStyle" TargetType="telerik:RadioButtonToolbarItemView">
        <Setter Property="DisplayOptions" Value="Text" />
        <Setter Property="VisualStateManager.VisualStateGroups">
            <VisualStateGroupList>
                <VisualStateGroup Name="CommonStates">
                    <VisualState Name="Normal" />
                    <VisualState Name="PointerOver">
                        <VisualState.Setters>
                            <Setter Property="BorderBrush" Value="HotPink" />
                            <Setter Property="BackgroundColor" Value="Pink" />
                        </VisualState.Setters>
                    </VisualState>
                    <VisualState Name="Selected">
                        <VisualState.Setters>
                            <Setter Property="BackgroundColor" Value="Blue" />
                            <Setter Property="TextColor" Value="LightBlue" />
                        </VisualState.Setters>
                    </VisualState>
                    <VisualState Name="SelectedDisabled">
                        <VisualState.Setters>
                            <Setter Property="BackgroundColor" Value="Gray" />
                            <Setter Property="TextColor" Value="LightGray" />
                        </VisualState.Setters>
                    </VisualState>
                    <VisualState Name="Disabled">
                        <VisualState.Setters>
                            <Setter Property="TextColor" Value="LightGray" />
                        </VisualState.Setters>
                    </VisualState>
                </VisualStateGroup>
            </VisualStateGroupList>
        </Setter>
    </Style>
</ContentView.Resources>

<VerticalStackLayout Margin="0,20">
    <telerik:RadToolbar x:Name="toolbar" >
        <telerik:GroupToolbarItem>
            <telerik:RadioButtonToolbarItem Text="12B" Style="{StaticResource RadioStyle}" />
            <telerik:RadioButtonToolbarItem Text="12C" Style="{StaticResource RadioStyle}" />
            <telerik:RadioButtonToolbarItem Text="12E" Style="{StaticResource RadioStyle}" />
        </telerik:GroupToolbarItem>
    </telerik:RadToolbar>
</VerticalStackLayout>
```

In this example, custom styles are defined in the `ContentView.Resources` section and applied to RadioButtonToolbarItems. The styles include visual states for `Normal`, `PointerOver`, `Selected`, and `Disabled` states, allowing for comprehensive customization of the toolbar items' appearance.

## See Also

- [VisualStateManager in .NET MAUI](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/visual-states?view=net-maui-9.0)
- [Toolbar Overview](https://docs.telerik.com/devtools/maui/controls/toolbar/overview)
