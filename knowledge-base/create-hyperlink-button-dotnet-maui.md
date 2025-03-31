---
title: Create a Hyperlink Button in .NET MAUI
description: Learn how to style a Telerik MAUI TemplatedButton to look like a hyperlink.
type: how-to
page_title: How to Style a TemplatedButton as a Hyperlink in .NET MAUI
slug: create-hyperlink-button-dotnet-maui
tags: templatedbutton, hyperlink, styling, .net maui, telerik ui for .net maui
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.0.0 | Telerik UI for .NET MAUI TemplatedButton | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

Styling a button to look and behave like a hyperlink can enhance the user interface of your application. 

This knowledge base article also answers the following questions:
- How to create a button that looks like a hyperlink in .NET MAUI?
- How to apply platform-specific styles to a button in .NET MAUI?
- How to use the Telerik MAUI TemplatedButton for creating hyperlinks?

## Solution

To create a hyperlink button in .NET MAUI using the [Telerik MAUI TemplatedButton](https://docs.telerik.com/devtools/maui/controls/templatedbutton/overview), follow these steps:

1. Define the button in XAML with the desired content and command. Apply the `HyperlinkButtonStyle` to the button.

    ```xml
    <telerik:RadTemplatedButton Content="Login"
                                Command="{Binding LogInCommand}"
                                Style="{StaticResource HyperlinkButtonStyle}"
                                WidthRequest="{OnPlatform WinUI=220, MacCatalyst=220}" />
    ```

2. Add the hyperlink button style and visual states to the page's resources. This includes setting the `TextColor`, `Background`, `BorderThickness`, and `Shadow` properties to mimic a hyperlink's appearance. Additionally, define visual states per platform to accommodate different user interactions such as Normal, PointerOver, Pressed, and Disabled states.

    ```xml
    <ResourceDictionary>

            <Color x:Key="PrimaryColor">#007AFF</Color>
            <Color x:Key="PrimaryColorDark">#5A91F7</Color>
            <Color x:Key="PrimaryColor_Alpha30">#4D007AFF</Color>
            <Color x:Key="PrimaryColor_Alpha38">#61007AFF</Color>
            <Color x:Key="PrimaryColor_Alpha50">#80007AFF</Color>
            <Color x:Key="PrimaryColor_Alpha60">#90007AFF</Color>

            <VisualStateGroupList x:Key="HyperlinkButton_VisualStates_Android">
                <VisualStateGroup Name="CommonStates">
                    <VisualState Name="Normal" />
                    <VisualState Name="PointerOver" />
                    <VisualState Name="Pressed">
                        <VisualState.Setters>
                            <Setter Property="telerik:RadTemplatedButton.Background" Value="#1F000000" />
                        </VisualState.Setters>
                    </VisualState>
                    <VisualState Name="Disabled">
                        <VisualState.Setters>
                            <Setter Property="telerik:RadTemplatedButton.TextColor" Value="#61000000" />
                        </VisualState.Setters>
                    </VisualState>
                </VisualStateGroup>
            </VisualStateGroupList>

            <VisualStateGroupList x:Key="HyperlinkButton_VisualStates_iOS">
                <VisualStateGroup Name="CommonStates">
                    <VisualState Name="Normal" />
                    <VisualState Name="PointerOver" />
                    <VisualState Name="Pressed">
                        <VisualState.Setters>
                            <Setter Property="telerik:RadTemplatedButton.TextColor" Value="{StaticResource PrimaryColor_Alpha50}" />
                        </VisualState.Setters>
                    </VisualState>
                    <VisualState Name="Disabled">
                        <VisualState.Setters>
                            <Setter Property="telerik:RadTemplatedButton.TextColor" Value="#61000000" />
                        </VisualState.Setters>
                    </VisualState>
                </VisualStateGroup>
            </VisualStateGroupList>

            <VisualStateGroupList x:Key="HyperlinkButton_VisualStates_MacCatalyst">
                <VisualStateGroup Name="CommonStates">
                    <VisualState Name="Normal" />
                    <VisualState Name="PointerOver" />
                    <VisualState Name="Pressed">
                        <VisualState.Setters>
                            <Setter Property="telerik:RadTemplatedButton.TextColor" Value="{StaticResource PrimaryColor_Alpha38}" />
                        </VisualState.Setters>
                    </VisualState>
                    <VisualState Name="Disabled">
                        <VisualState.Setters>
                            <Setter Property="telerik:RadTemplatedButton.TextColor" Value="#61000000" />
                        </VisualState.Setters>
                    </VisualState>
                </VisualStateGroup>
            </VisualStateGroupList>

            <VisualStateGroupList x:Key="HyperlinkButton_VisualStates_WinUI">
                <VisualStateGroup Name="CommonStates">
                    <VisualState Name="Normal" />
                    <VisualState Name="PointerOver">
                        <VisualState.Setters>
                            <Setter Property="telerik:RadTemplatedButton.Background" Value="{AppThemeBinding Light='#80F9F9F9', Dark='#15FFFFFF' }" />
                        </VisualState.Setters>
                    </VisualState>
                    <VisualState Name="Pressed">
                        <VisualState.Setters>
                            <Setter Property="telerik:RadTemplatedButton.TextColor" Value="{StaticResource PrimaryColor_Alpha60}" />
                            <Setter Property="telerik:RadTemplatedButton.Background" Value="#4DF9F9F9" />
                        </VisualState.Setters>
                    </VisualState>
                    <VisualState Name="Disabled">
                        <VisualState.Setters>
                            <Setter Property="telerik:RadTemplatedButton.TextColor" Value="{StaticResource PrimaryColor_Alpha38}" />
                            <Setter Property="telerik:RadTemplatedButton.Background" Value="#4DF9F9F9" />
                        </VisualState.Setters>
                    </VisualState>
                </VisualStateGroup>
            </VisualStateGroupList>

            <Style x:Key="HyperlinkButtonStyle" TargetType="telerik:RadTemplatedButton">
                <Setter Property="TextColor" Value="{AppThemeBinding Light={StaticResource PrimaryColor}, Dark={StaticResource PrimaryColorDark}}" />
                <Setter Property="Background" Value="Transparent" />
                <Setter Property="BorderThickness" Value="0" />
                <Setter Property="Shadow" Value="{x:Null}" />
                <Setter Property="VisualStateManager.VisualStateGroups"
                        Value="{OnPlatform Android={StaticResource HyperlinkButton_VisualStates_Android},
                                           iOS={StaticResource HyperlinkButton_VisualStates_iOS},
                                           MacCatalyst={StaticResource HyperlinkButton_VisualStates_MacCatalyst},
                                           WinUI={StaticResource HyperlinkButton_VisualStates_WinUI}}" />
    </ResourceDictionary>
    ```

The provided code snippets demonstrate how to create a TemplatedButton that looks like a hyperlink and configure it to change appearance based on user interaction and platform. Remember to define the colors and visual states in your application's resources to apply them correctly.

## See Also
- [TemplatedButton Documentation](https://docs.telerik.com/devtools/maui/controls/templatedbutton/overview)
- [Styling in .NET MAUI](hhttps://learn.microsoft.com/en-us/dotnet/maui/user-interface/styles/xaml?view=net-maui-9.0)
