---
title: Changing Theme Swatch at Runtime in C# Code
description: Learn how to change the Theme Colors (Swatches) at runtime using C# code.
type: how-to
page_title: Modify Theme Swatch Dynamically in .NET MAUI
meta_title: Modify Theme Swatch Dynamically in .NET MAUI
slug: change-theme-swatch-runtime-dotnet-maui
tags: teleriktheme, telerikthemresources, apptheme, customswatch, netmaui
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.0 | Telerik UI for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to change the Theme Colors (Swatches) at runtime using C# code in a .NET MAUI application.

This knowledge base article also answers the following questions:
- How to switch theme colors at runtime in .NET MAUI?
- How to dynamically apply theme swatches using C# in Telerik UI for .NET MAUI?

## Solution

To change the theme swatch dynamically, set the `TelerikThemeResources.AppTheme` to the desired pre-defined theme.

Below is an example to switch from the `TelerikPurple` theme to the `TelerikTurquoise` theme and merge a custom swatch defined in a `CustomTelerikSwatch.xaml` file.

1. Apply the custom swatch at runtime:

```csharp
public partial class App : Application
    {
        public App()
        {
            InitializeComponent();
            TelerikThemeResources.AppTheme = TelerikTheme.TelerikPurple;
        }

        protected override Window CreateWindow(IActivationState? activationState)
        {
            return new Window(new AppShell());
        }
    }
```

2. Invoke the method to change the theme and swatch during runtime.

```csharp
TelerikThemeResources.AppTheme = TelerikTheme.TelerikTurquoise;
TelerikThemeResources.Current.MergedDictionaries.Add(new CustomTelerikSwatch());
```

## See Also

- [Styling and Themes - Customize the Theme Colors (Swatches)](https://docs.telerik.com/devtools/maui/styling-and-themes/customize-the-theme#customizing-the-theme-colors-swatches)
- [Change Telerik Theme at Runtime](https://docs.telerik.com/devtools/maui/knowledge-base/change-telerik-theme-runtime)
