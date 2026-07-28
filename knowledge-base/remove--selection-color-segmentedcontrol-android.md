---
title: Remove the Default Selection Color in SegmentedControl on Android
description: Learn how to remove the selection color block in SegmentedControl for UI for .NET MAUI on Android.
type: how-to
page_title: Remove Selection Color in SegmentedControl on Android
meta_title: Remove Selection Color in SegmentedControl for UI for .NET MAUI
slug: remove--selection-color-segmentedcontrol-android
tags: segmentedcontrol, ui-for-dotnet-maui, visual-states, ripple-effect, styling
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | ---- | ---- |
| 14.1.0 | Telerik UI for .NET MAUI SegmentedControl | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

When using [SegmentedControl](https://www.telerik.com/maui-ui/documentation/controls/segmentedcontrol/overview) for UI for .NET MAUI on Android, a selection color block appears when selecting a segment. This behavior occurs due to the default visual states and ripple effects applied to the control. This article explains how to remove the default selection color block on Android and customize the visual states to achieve the desired appearance.

This knowledge base article also answers the following questions:
- How to remove the ripple effect in SegmentedControl on Android?
- How to style the SegmentedControl visual states in UI for .NET MAUI?
- How to customize SegmentedControl selection colors on Android?

## Solution

To remove the default selection color block and customize the visual states in SegmentedControl on Android, follow these steps:

1. Define a custom `VisualStateGroupList` in the `ContentPage.Resources`. Set styles for different visual states, including `Pressed` and `SelectedPressed`, to make them transparent or match your desired design.

2. Use the `telerikTheming:RadEffects` namespace to manage the ripple effect. Set the `RippleMode` to `None` and `RippleColor` to `Transparent`.

3. Apply the `VisualStateGroupList` to the `RadSegmentedControlItemView` using the `VisualStateManager.VisualStateGroups` property.

Here is the complete XAML structure:

```xaml
<ContentPage.Resources>
    <ResourceDictionary>
        <VisualStateGroupList x:Key="SegmentedControlItemViewVisualStates_Android">
            <VisualStateGroup Name="CommonStates">
                <VisualState Name="Normal" />
                <VisualState Name="Pressed">
                    <VisualState.Setters>
                        <Setter Property="telerik:RadSegmentedControlItemView.BackgroundColor" Value="Transparent" />
                    </VisualState.Setters>
                </VisualState>
                <VisualState Name="SelectedPressed">
                    <VisualState.Setters>
                        <Setter Property="telerikTheming:RadEffects.RippleColor" Value="Transparent" />
                        <Setter Property="telerik:RadSegmentedControlItemView.BackgroundColor" Value="{DynamicResource RadPrimaryColorLighten12}" />
                    </VisualState.Setters>
                </VisualState>
                <VisualState Name="Selected" />
                <VisualState Name="Disabled">
                    <VisualState.Setters>
                        <Setter Property="telerik:RadSegmentedControlItemView.TextColor" Value="{DynamicResource RadSegmentedControlDisabledTextColor}" />
                    </VisualState.Setters>
                </VisualState>
                <VisualState Name="DisabledSelected">
                    <VisualState.Setters>
                        <Setter Property="telerik:RadSegmentedControlItemView.TextColor" Value="{DynamicResource RadSegmentedControlDisabledTextColor}" />
                        <Setter Property="telerik:RadSegmentedControlItemView.SelectedTextColor" Value="{DynamicResource RadSegmentedControlDisabledSelectedTextColor}" />
                    </VisualState.Setters>
                </VisualState>
            </VisualStateGroup>
        </VisualStateGroupList>
        <Style TargetType="telerik:RadSegmentedControl">
            <Setter Property="SelectedIndex" Value="0" />
            <Setter Property="CornerRadius" Value="8" />
            <Setter Property="Padding" Value="5" />
            <Setter Property="BackgroundColor" Value="{AppThemeBinding Light=Yellow, Dark=Gray}" />
            <Setter Property="ItemViewStyle">
                <Setter.Value>
                    <Style TargetType="telerik:RadSegmentedControlItemView">
                        <Setter Property="TextColor" Value="{AppThemeBinding Light=Black, Dark=White}" />
                        <Setter Property="SelectedTextColor" Value="White" />
                        <Setter Property="VisualStateManager.VisualStateGroups"
                                Value="{StaticResource SegmentedControlItemViewVisualStates_Android}" />
                        <Setter Property="telerikTheming:RadEffects.RippleMode" Value="None" />
                        <Setter Property="telerikTheming:RadEffects.RippleColor" Value="Transparent" />
                    </Style>
                </Setter.Value>
            </Setter>
            <Setter Property="SelectionIndicatorStyle">
                <Setter.Value>
                    <Style TargetType="telerik:RadBorder">
                        <Setter Property="BackgroundColor" Value="{StaticResource Primary}" />
                        <Setter Property="CornerRadius" Value="8" />
                    </Style>
                </Setter.Value>
            </Setter>
            <Setter Property="SeparatorStyle">
                <Setter.Value>
                    <Style TargetType="telerik:RadBorder">
                        <Setter Property="BackgroundColor" Value="Transparent" />
                    </Style>
                </Setter.Value>
            </Setter>
        </Style>
    </ResourceDictionary>
</ContentPage.Resources>

<VerticalStackLayout>
    <telerik:RadSegmentedControl>
        <telerik:RadSegmentedControl.ItemsSource>
            <x:Array Type="{x:Type x:String}">
                <x:String>Popular</x:String>
                <x:String>Library</x:String>
                <x:String>Playlists</x:String>
                <x:String>Friends</x:String>
            </x:Array>
        </telerik:RadSegmentedControl.ItemsSource>
    </telerik:RadSegmentedControl>
</VerticalStackLayout>
```

Ensure the `telerikTheming` namespace is included in your XAML:

```xaml
xmlns:telerikTheming="clr-namespace:Telerik.Maui.Controls.Theming;assembly=Telerik.Maui.Controls"
```

To further customize the appearance, review the styles and templates in the Telerik theming file located at `TelerikTheming/Styles/Platform/SegmentedControl.xaml`.

## See Also

- [SegmentedControl Documentation](https://www.telerik.com/maui-ui/documentation/controls/segmentedcontrol/overview)
- [Telerik Theming Documentation](https://www.telerik.com/maui-ui/documentation/styling-and-themes/overview) 
- [SegmentedControl Visual States](https://www.telerik.com/maui-ui/documentation/controls/segmentedcontrol/visual-states)
