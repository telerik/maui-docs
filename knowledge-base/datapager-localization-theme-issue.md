---
title: Localization Not Applying to Elements in DataPager When Using Telerik Localization Manager and Theme
description: Resolve the issue where localization does not apply to DataPager elements when using Telerik Localization Manager and applying a Telerik theme.
type: troubleshooting
page_title: Fix Localization Issue in DataPager When Using Telerik Localization Manager and Theme
meta_title: Fix Localization Issue in DataPager When Using Telerik Localization Manager and Theme
slug: datapager-localization-theme-issue
tags: datapager, ui for .net maui, localization, theme, localization manager
res_type: kb
---

## Environment


| Version | Product | Author | 
| --- | --- | ---- | 
| 12.0.0 | Telerik UI for .NET MAUI DataPager | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I observe that the localization does not apply to some elements in the [DataPager](https://www.telerik.com/maui-ui/documentation/controls/datapager/overview) when using the Telerik Localization Manager and applying a Telerik theme. For example, localized strings may not appear correctly in certain parts of the DataPager.

## Cause

The Telerik Localization Manager is set after merging the Telerik theme resources, which results in the localization not being applied to some elements.

## Solution

Set the Telerik Localization Manager before merging the Telerik theme resources in the `App.xaml.cs` file.

1. Open the `App.xaml.cs` file in your project.
2. Add the code snippet below to ensure the localization manager is set before the theme resources:

```csharp
public partial class App : Application
{
    public App()
    {
        // Set the localization manager.
        TelerikLocalizationManager.Manager.ResourceManager = AppResources.ResourceManager;

        InitializeComponent();

        // Apply Telerik theme resources.
        TelerikThemeResources.AppTheme = TelerikTheme.PlatformDark;

        if (TelerikThemeResources.AppTheme.ToString().EndsWith("Dark"))
        {
            Application.Current.UserAppTheme = AppTheme.Dark;
        }
    }

    protected override Window CreateWindow(IActivationState? activationState)
    {
        return new Window(new MainPage());
    }
}
```

Ensure the `AppResources.ResourceManager` points to your localization resource file.

## See Also

- [DataPager Documentation](https://www.telerik.com/maui-ui/documentation/controls/datapager/overview)
- [Localization in UI for .NET MAUI](https://www.telerik.com/maui-ui/documentation/globalization-localization)
- [Themes in UI for .NET MAUI](https://www.telerik.com/maui-ui/documentation/styling-and-themes/overview)
