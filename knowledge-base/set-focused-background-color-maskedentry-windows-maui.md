---
title: Setting the Focused Background Color of a MaskedEntry Control on Windows
description: Learn how to set the focused background color of a MaskedEntry control on Windows in the MaskedEntry for .NET MAUI.
type: how-to
page_title: How to Set the Focused Background Color of a MaskedEntry Control on Windows | MaskedEntry for .NET MAUI
slug: set-focused-background-color-maskedentry-windows-maui
tags: maskedentry, windows, background color, focused, control
res_type: kb
---

## Environment

| Property | Value |
|----------|-------|
| Product | MaskedEntry for .NET MAUI |
| Version | 6.6.0 |

## Description

I want to set the focused background color of a MaskedEntry control on Windows in my .NET MAUI application. By default, when I tab into the control, the focused background color reverts to white even after setting the background color to black. Changing the background using the 'Focused' visual state does not work either.

## Solution

To set the focused background color of a MaskedEntry control on Windows in a .NET MAUI application, follow these steps:

1. Create a custom ResourceDictionary that contains the desired adjustments for the visual states.
2. Merge this ResourceDictionary in the `Platforms/Windows/App.xaml` file.

Here is an example:

1. Create a new file named `CustomStyles.xaml` in the `Platforms/Windows` folder of your .NET MAUI application.

2. Add the following XAML code to the `CustomStyles.xaml` file:

```xml
<ResourceDictionary xmlns="http://xamarin.com/schemas/2014/forms"
                    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml">
    <Style TargetType="TextBox">
        <Setter Property="Background" Value="Black" />
        <Setter Property="BorderBrush" Value="Black" />
        <Setter Property="Foreground" Value="White" />
        <Setter Property="Padding" Value="5" />
    </Style>
    <Style TargetType="TextBox" x:Key="FocusVisualStyle">
        <Setter Property="Background" Value="Black" />
        <Setter Property="Foreground" Value="White" />
    </Style>
</ResourceDictionary>
```

3. Open the `Platforms/Windows/App.xaml` file and add the following line inside the `ResourceDictionary` section:

```xml
    <maui:MauiWinUIApplication.Resources>
        <ResourceDictionary>
            <!--Replace the resources of Telerik-->
            <ResourceDictionary.ThemeDictionaries>
                <ResourceDictionary x:Key="Default">
                    <winui:UserThemeResources x:Key="ResourceLoaderInitializer"
                                              LightResourcesPath="ms-appx:///Platforms/Windows/CustomStyles.xaml"/>
                </ResourceDictionary>
            </ResourceDictionary.ThemeDictionaries>
        </ResourceDictionary>
    </maui:MauiWinUIApplication.Resources>
```

4. Save the changes and rebuild your .NET MAUI application.

Now, when you tab into the MaskedEntry control on Windows, the focused background color will be set to black.

## Notes

- By creating a custom ResourceDictionary and merging it in the `Platforms/Windows/App.xaml` file, you can override the default visual states of the MaskedEntry control and customize its appearance on Windows.
- Make sure to adjust the background color values in the `CustomStyles.xaml` file according to your desired color scheme.

## See Also

- [Customizing the Visual Appearance of Controls in .NET MAUI](https://docs.microsoft.com/en-us/dotnet/maui/user-interface/customize-controls/)
