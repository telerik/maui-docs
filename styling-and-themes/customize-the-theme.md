---
title: Customizing the Theme Colors
page_title: Customizing the Theme Colors
description: Learn how to customize the colors of the Telerik theme for your .NET MAUI application and alter the default appearance of the UI for .NET MAUI components.
slug: themes-customization
tags: telerik,.net maui,theme,custom
position: 1
---

# Customizing the Theme Colors (Swatches)

The Telerik UI for .NET MAUI themes are flexible and allow you to customize and adjust them to meet the specific application requirements.

When it comes to implementing your brand colors, modifying the swatches (the color variations) of the Telerik allows you to apply the desired tones to all Telerik UI for .NET MAUI controls.

> If you need to customize the styles only of a specific control or collection of controls, you can also [modify the control-specific theme resources]({%slug theme-component-styles-customization %}).

To customize the Telerik UI for .NET MAUI theme colors:

1. Copy the desired theme resources to a new resource dictionary and apply your changes.
1. Merge the new resource dictionary after the built-in Telerik theme resources.

Before proceeding with the next steps, make sure the [Telerik theming is enabled]({%slug themes-overview%}#using-the-maui-theming).

## Copy and Modify the Theme Resources

To customize the colors of the Telerik theme, use the available color swatch resource dictionaries in the `\TelerikTheming\Colors\Telerik\Swatches\` folder as a starting point. These files are generated when you enable the Telerik theming and serve as a reference for your customizations.

1. Go to the `Resources\Styles` folder and create a resource dictionary file called `CustomTelerikSwatch.xaml`. The new file must have no code-behind file, similar to the `Styles.xaml` and `Colors.xaml` files in a project that uses the default MAUI application template by Microsoft.

1. Choose the [color swatch]({%slug themes-overview%}#swatch) of the Telerik theme that you will use as a starting point for your color customizations, for example, the Main swatch represented by the `\TelerikTheming\Colors\Telerik\Swatches\Main.xaml` resource dictionary.

1. Copy the colors that you want to modify from the color swatch and paste them into the newly created `Resources\Styles\CustomTelerikSwatch.xaml` file. Apply the required changes based on your design requirements. For example, you can modify the primary colors of a swatch:

```XAML
<?xml version="1.0" encoding="UTF-8" ?>
<?xaml-comp compile="true" ?>
<ResourceDictionary 
    xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
    xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui">

    <!-- Primary -->
    <Color x:Key="RadPrimarySubtleColor">#D0E3EE</Color>
    <Color x:Key="RadPrimarySubtleHoverColor">#B8D5E6</Color>
    <Color x:Key="RadPrimarySubtleActiveColor">#A0C7DE</Color>
    <Color x:Key="RadPrimaryColor">#74AC12</Color>
    <Color x:Key="RadPrimaryHoverColor">#689B10</Color>
    <Color x:Key="RadPrimaryActiveColor">#5D8A0E</Color>
    <Color x:Key="RadPrimaryEmphasisColor">#ACCD71</Color>
    <Color x:Key="RadPrimaryOnSubtleColor">#2E4507</Color>
    <Color x:Key="RadOnPrimaryColor">#FFFFFF</Color>
    <Color x:Key="RadPrimaryOnSurfaceColor">#74AC12</Color>

    <telerik:ColorFilter x:Key="RadPrimaryColorAlpha4" Color="{StaticResource RadPrimaryColor}" Alpha="0.04" />
    <telerik:ColorFilter x:Key="RadPrimaryColorAlpha16" Color="{StaticResource RadPrimaryColor}" Alpha="0.16" />
    <telerik:ColorFilter x:Key="RadPrimaryColorDarken4" Color="{StaticResource RadPrimaryColor}" Lighten="-0.04" />
    <telerik:ColorFilter x:Key="RadPrimaryColorDarken12" Color="{StaticResource RadPrimaryColor}" Lighten="-0.12" />
</ResourceDictionary>
```

## Merge the New Resource Dictionary

Once you customize the colors in the newly created `Resources\Styles\CustomTelerikSwatch.xaml` resource dictionary, configure the application to use them: add the new resource dictionary to the `App.xaml` and make sure you merge your customized `CustomTelerikSwatch.xaml` resource dictionary after the `TelerikTheming`:

```XAML
<Application.Resources>
    <ResourceDictionary>
        <ResourceDictionary.MergedDictionaries>
            <ResourceDictionary Source="Resources/Styles/Colors.xaml" />
            <ResourceDictionary Source="Resources/Styles/Styles.xaml" />
            <local:TelerikTheming />

            <!-- Add your customized colors after the TelerikTheming resources.-->
            <ResourceDictionary Source="Resources/Styles/CustomTelerikSwatch.xaml" />
        </ResourceDictionary.MergedDictionaries>
    </ResourceDictionary>
</Application.Resources>
```

The next image illustrates the effects of customizing the primary color of the theme swatch:

![Telerik .NET MAUI Theming Custom Colors](images/telerik-theming-customized.png)

## See Also

- [Customizing the Control-Specific Theme Resources]({%slug theme-component-styles-customization %})
- [Themes Overview]({%slug themes-overview%})
