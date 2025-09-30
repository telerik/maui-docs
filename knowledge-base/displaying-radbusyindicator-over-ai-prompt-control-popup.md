---
title: Displaying BusyIndicator In AIPrompt Control Popup
description: Learn how to ensure BusyIndicator displays correctly over the AIPrompt Control popup in a UI for .NET MAUI application.
type: how-to
page_title: Adding Custom BusyIndicator In AI Prompt Popup
meta_title: Adding Custom BusyIndicator In AI Prompt Popup
slug: displaying-busyindicator-over-ai-prompt-control-popup
tags: busyindicator, ai prompt, popup, threading, controltemplate, ui-for-net-maui
res_type: kb
ticketid: 1697962
---

## Environment

| Version | Product |
| --- | --- |
| 11.1.0 | BusyIndicator for .NET MAUI |
| 11.1.0 | AIPrompt for .NET MAUI |

## Description

When using the [`RadBusyIndicator`](https://docs.telerik.com/devtools/maui/controls/busyindicator/overview) in a UI for .NET MAUI application, it may fail to display over the AIPrompt Control popup. The issue occurs because the AIPrompt Control's popup has a higher Z-index, which causes the BusyIndicator to appear behind the popup. 

This knowledge base article also answers the following questions:
- How to display BusyIndicator inside AIPrompt Control popup?
- Why does BusyIndicator appear behind AIPrompt Control popup?
- How to fix Z-index issues with BusyIndicator and AIPrompt popup?

## Solution

To ensure the `RadBusyIndicator` displays correctly over the AIPrompt Control popup, customize the `ControlTemplate` of the AIPrompt Control and embed the BusyIndicator directly within the popup's layout.

### Steps to Resolve

1. Copy the `ControlTemplate` of the AIPrompt Control (see below).
2. Insert the BusyIndicator into the visual tree of the AIPrompt Control's popup area.
3. Update the `ControlTemplate` in your project.

### Example Code

Below is an adjusted `MainPage.xaml` that ensures the BusyIndicator is part of the AIPrompt Control's popup:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
             xmlns:vm="clr-namespace:AIPromptDemo"
             x:Class="AIPromptDemo.MainPage"
             x:Name="ThisPage">

    <Grid x:DataType="vm:MainPageViewModel"
          Padding="30,0">
        <telerik:RadAIPromptButton HeightRequest="25"
                                   WidthRequest="55"
                                   Content="Ask AI"
                                   ...>
            <telerik:RadAIPrompt x:Name="aiPrompt"
                                 HeightRequest="700"
                                 ...>
            </telerik:RadAIPrompt>
        </telerik:RadAIPromptButton>
    </Grid>

    <ContentPage.Resources>
        <ControlTemplate x:Key="AIPromptPopupContentViewControlTemplate">
            <telerik:RadBorder BackgroundColor="{TemplateBinding BackgroundColor}" Background="{TemplateBinding Background}" BorderColor="{TemplateBinding BorderColor}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" CornerRadius="{TemplateBinding CornerRadius}" Padding="{TemplateBinding ContentPadding}" Shadow="{StaticResource AIPromptPopupContentViewShadow}">
                <Grid RowDefinitions="48, *">
                    <ContentPresenter Grid.RowSpan="2" />
                    <Grid Padding="8" Margin="8" HorizontalOptions="End" VerticalOptions="Center">
                        <View.GestureRecognizers>
                            <TapGestureRecognizer Command="{TemplateBinding ActualClosePopupCommand}" />
                        </View.GestureRecognizers>
                        <telerik:RadTemplatedButton Style="{TemplateBinding ActualClosePopupButtonStyle}" />
                    </Grid>

                    <!-- CUSTOMIZATION
                    Adding this RadBusyIndicator to the default ControlTemplate
                    It is important to recognize that we are binding the control's properties to the page view model properties by setting the BindingContext -->
                    <telerik:RadBusyIndicator x:Name="loadingIndicatorHeat" 
                                              IsVisible="{Binding ShowBusyIndicator}"
                                              IsBusy="{Binding ShowBusyIndicator}"
                                              BindingContext="{Binding BindingContext, Source={x:Reference ThisPage}}"
                                              Grid.Row="0" Grid.RowSpan="2" AnimationType="Animation9" AnimationContentColor="White" AnimationContentHeightRequest="50" AnimationContentWidthRequest="50" BackgroundColor="#AA000000" >
                        <telerik:RadBusyIndicator.BusyContent>
                            <Label Text="Loading Data..." TextColor="White" FontSize="16" />
                        </telerik:RadBusyIndicator.BusyContent>
                        <telerik:RadBusyIndicator.BusyContentTemplate>
                            <ControlTemplate>
                                <Grid RowDefinitions="*,*,*">
                                    <Border Grid.Row="0" Stroke="Black" StrokeThickness="4" Background="Black" Padding="16,7,16,14" HorizontalOptions="Center" VerticalOptions="End">
                                        <Border.StrokeShape>
                                            <RoundRectangle CornerRadius="5,5,5,5" />
                                        </Border.StrokeShape>
                                        <Grid RowSpacing="5">
                                            <Grid.RowDefinitions>
                                                <RowDefinition Height="Auto" />
                                                <RowDefinition Height="Auto" />
                                                <RowDefinition Height="*" />
                                            </Grid.RowDefinitions>
                                            <ContentPresenter Content="{TemplateBinding Path=AnimationContent}" />
                                            <ContentPresenter Grid.Row="1" Content="{TemplateBinding Path=BusyContent}" HorizontalOptions="Center" />
                                        </Grid>
                                    </Border>
                                </Grid>
                            </ControlTemplate>
                        </telerik:RadBusyIndicator.BusyContentTemplate>
                    </telerik:RadBusyIndicator>
                </Grid>
            </telerik:RadBorder>
        </ControlTemplate>

        <Shadow x:Key="AIPromptPopupContentViewShadow"
                Offset="{OnPlatform Default='0, 0', MacCatalyst='0, 8', WinUI='0, 8'}"
                Radius="{OnPlatform Default=0, MacCatalyst=40, WinUI=16}"
                Brush="{OnPlatform Default=Transparent, MacCatalyst=#40000000, WinUI=#24000000}" />

        <Style x:Key="RadTemplatedButtonStyle" TargetType="telerik:RadTemplatedButton">
            <Setter Property="TextColor" Value="{DynamicResource RadOnBaseColor}" />
            <Setter Property="Background" Value="{DynamicResource RadBaseBrush}" />
            <Setter Property="BorderBrush" Value="{DynamicResource RadBorderColor}" />
            <Setter Property="BorderThickness" Value="1" />
            <Setter Property="Padding" Value="{OnPlatform Android='9, 11', iOS='9, 12.5', MacCatalyst='9, 6.5', WinUI='9, 5'}" />
            <Setter Property="CornerRadius" Value="4" />
            <Setter Property="Shadow" Value="{x:Null}" />
            <Setter Property="VisualStateManager.VisualStateGroups">
                <VisualStateGroupList>
                    <VisualStateGroup x:Name="CommonStates">
                        <VisualState x:Name="Normal">
                            <VisualState.Setters>
                                <Setter Property="telerik:RadTemplatedButton.Background" Value="{DynamicResource RadBaseBrush}" />
                            </VisualState.Setters>
                        </VisualState>
                        <VisualState x:Name="PointerOver">
                            <VisualState.Setters>
                                <Setter Property="telerik:RadTemplatedButton.Background" Value="{DynamicResource RadBaseHoverBrush}" />
                            </VisualState.Setters>
                        </VisualState>
                        <VisualState x:Name="Pressed">
                            <VisualState.Setters>
                                <Setter Property="telerik:RadTemplatedButton.Background" Value="{DynamicResource RadBaseActiveBrush}" />
                            </VisualState.Setters>
                        </VisualState>
                        <VisualState x:Name="Disabled">
                            <VisualState.Setters>
                                <Setter Property="telerik:RadTemplatedButton.Background" Value="{DynamicResource RadBaseBrush}" />
                                <Setter Property="Opacity" Value="0.6" />
                            </VisualState.Setters>
                        </VisualState>
                    </VisualStateGroup>
                </VisualStateGroupList>
            </Setter>
        </Style>

        <Style x:Key="RadAIPromptClosePopupButtonStyle" TargetType="telerik:RadTemplatedButton" BasedOn="{StaticResource RadTemplatedButtonStyle}">
            <Setter Property="BorderThickness" Value="0" />
            <Setter Property="Padding" Value="0" />
        </Style>

        <Style x:Key="RadAIPromptPopupContentViewStyle" TargetType="telerik:AIPromptPopupContentView">
            <Setter Property="ControlTemplate" Value="{StaticResource AIPromptPopupContentViewControlTemplate}" />
            <Setter Property="BackgroundColor" Value="{DynamicResource RadSurfaceAltColor}" />
            <Setter Property="ClosePopupButtonStyle" Value="{StaticResource RadAIPromptClosePopupButtonStyle}" />
            <Setter Property="CornerRadius" Value="0" />
        </Style>

        <Style x:Key="RadAIPromptButtonStyle" TargetType="telerik:RadAIPromptButton">
            <Setter Property="WidthRequest" Value="36" />
            <Setter Property="HeightRequest" Value="36" />
            <Setter Property="FontFamily" Value="{x:Static telerik:TelerikFont.Name}" />
            <Setter Property="FontSize" Value="16" />
            <Setter Property="TextColor" Value="{DynamicResource RadOnPrimaryColor}" />
            <Setter Property="Background" Value="{DynamicResource RadPrimaryColor}" />
            <Setter Property="BorderBrush" Value="Transparent" />
            <Setter Property="Content" Value="{x:Static telerik:TelerikFont.IconSparkle}" />
            <Setter Property="CornerRadius" Value="18" />
            <Setter Property="Padding" Value="0" />
            <Setter Property="HorizontalTextAlignment" Value="Center" />
            <Setter Property="VerticalTextAlignment" Value="Center" />
            <Setter Property="PopupContentViewStyle" Value="{StaticResource RadAIPromptPopupContentViewStyle}" />
            <Setter Property="VisualStateManager.VisualStateGroups">
                <VisualStateGroupList>
                    <VisualStateGroup x:Name="CommonStates">
                        <VisualState x:Name="Normal">
                            <VisualState.Setters>
                                <Setter Property="Background" Value="{DynamicResource RadPrimaryColor}" />
                            </VisualState.Setters>
                        </VisualState>
                        <VisualState x:Name="PointerOver">
                            <VisualState.Setters>
                                <Setter Property="Background" Value="{DynamicResource RadPrimaryHoverColor}" />
                            </VisualState.Setters>
                        </VisualState>
                        <VisualState x:Name="Pressed">
                            <VisualState.Setters>
                                <Setter Property="Background" Value="{DynamicResource RadPrimaryActiveColor}" />
                            </VisualState.Setters>
                        </VisualState>
                        <VisualState x:Name="Disabled">
                            <VisualState.Setters>
                                <Setter Property="Background" Value="{DynamicResource RadPrimaryColor}" />
                                <Setter Property="Opacity" Value="0.6" />
                            </VisualState.Setters>
                        </VisualState>
                    </VisualStateGroup>
                </VisualStateGroupList>
            </Setter>
        </Style>

        <Style TargetType="telerik:RadAIPromptButton" BasedOn="{StaticResource RadAIPromptButtonStyle}" />
    </ContentPage.Resources>
</ContentPage>
```

>note Important: ControlTemplates change over time as the control itself evolves and his example was built using v11.1.0. If you need help locating this, please open a Support Ticket. While Technical Support is unable to assist with your customizations, they can provide you with a copy of the XAML.

## See Also

- [`RadBusyIndicator` Documentation](https://docs.telerik.com/devtools/maui/controls/busyindicator/overview)
- [AIPrompt Control Overview](https://docs.telerik.com/devtools/maui/controls/aiprompt/overview)
- [Customizing Control Templates in .NET MAUI](https://learn.microsoft.com/en-us/dotnet/maui/fundamentals/controltemplate)

