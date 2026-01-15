---
title: Applying Dark Theme to RadDataGrid Filtering UI in UI for .NET MAUI
description: Learn how to configure the RadDataGrid Filtering UI to respond properly to a dark theme in UI for .NET MAUI.
type: how-to
page_title: Configure RadDataGrid Filtering UI for Dark Theme in UI for .NET MAUI
meta_title: Configure RadDataGrid Filtering UI for Dark Theme in UI for .NET MAUI
slug: configure-raddatagrid-dark-theme-filtering-ui
tags: ui-for-net-maui, raddatagrid, filtering, dark-theme, theming
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | --- | ---- | 
| 12.1.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

When using the default filter in RadDataGrid on a device or app dark theme, the text color changes appropriately, but the background color does not adjust, making the text difficult or impossible to read. If you want to enable proper dark theme behavior for Telerik controls, you need to configure a Telerik dark theme swatch.

This knowledge base article also answers the following questions:
- How to apply Telerik dark theme to DataGrid in UI for .NET MAUI?
- How to configure DataGrid filtering UI for a dark theme?
- How to enable runtime theme changes in UI for .NET MAUI?

## Solution

To apply a dark theme to the DataGrid Filtering UI, follow these steps:

1. Enable Telerik theming in your project. Open the `.csproj` file and ensure the Telerik theming mechanism is included.

    ```xml
     <UseTelerikTheming>true</UseTelerikTheming>
    ```

2. Add the theme resource to the `App.xaml` file. Example:

    ```xml
    <Application.Resources>
        <ResourceDictionary>
            <telerik:TelerikTheme x:Key="TelerikTheme" />
        </ResourceDictionary>
    </Application.Resources>
    ```

3. Set the dark theme swatch in the `App.xaml.cs` file. Example:

    ```csharp
    public App()
    {
        InitializeComponent();
        if (Application.Current.RequestedTheme == AppTheme.Dark)
	{
		TelerikThemeResources.AppTheme = TelerikTheme.PlatformDark;
	}
	else TelerikThemeResources.AppTheme = TelerikTheme.PlatformLight;
    }
    ```

4. Configure runtime theme changes based on device/app theme. Refer to the detailed guide provided in the [Change Telerik Theme at Runtime](https://www.telerik.com/maui-ui/documentation/knowledge-base/change-telerik-theme-runtime) documentation.

5. For Windows platform, ensure the app dark theme is set properly in `Platforms/Windows/App.xaml.cs`. Example:

    ```csharp
    Application.Current.RequestedTheme = ApplicationTheme.Dark;
    ```

## See Also

- [Styling and Themes Overview](https://www.telerik.com/maui-ui/documentation/styling-and-themes/overview)
- [Change Telerik Theme at Runtime](https://www.telerik.com/maui-ui/documentation/knowledge-base/change-telerik-theme-runtime)
- [UI for .NET MAUI DataGrid Documentation](https://www.telerik.com/maui-ui/documentation/controls/datagrid/overview)
