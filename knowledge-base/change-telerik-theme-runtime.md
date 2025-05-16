---
title: Changing the Telerik Theme at Runtime Based on the Device Theme
page_title: Changing the Telerik Theme at Runtime Based on the Device Theme - .NET MAUI Knowledge Base
description: Learn how to dynamically switch the light/dark mode of the Telerik theme based on the theme of the target device.
type: how-to
slug: change-telerik-theme-runtime
tags: maui, theming, dark mode, dotnet maui, runtime
res_type: kb
---

## Environment

<table>
	<tbody>
    <tr>
      <td>Product</td>
      <td>Progress® Telerik® UI for .NET MAUI</td>
    </tr>
  	<tr>
  		<td>Product Version</td>
  		<td>11.0.0</td>
  	</tr>
	</tbody>
</table>

## Description

How can I change the Telerik theme at runtime based on the device's theme and dynamically switch between dark and light modes?

## Solution

To ensure that the Telerik .NET MAUI controls respond to app theme changes correctly:

**1.** [Enable the Telerik Theming in your app]({%slug themes-overview%}#using-the-maui-theming).

**2.** Detect the current system theme&mdash;use the `Application.RequestedTheme` property to get the current `AppTheme`.

**2.1** Example with loading the light or dark `Purple` swatch of the `Telerik` theme:

```C#
private void ApplyTelerikTheme()
{

	if (Application.Current.RequestedTheme == AppTheme.Dark)
	{
		TelerikThemeResources.AppTheme = TelerikTheme.TelerikPurpleDark;
	}
	else TelerikThemeResources.AppTheme = TelerikTheme.TelerikPurple;
}
```

**2.2** Example with loading the light or dark swatch of the `Platform` theme:

```C#
private void ApplyTelerikTheme()
{

	if (Application.Current.RequestedTheme == AppTheme.Dark)
	{
		TelerikThemeResources.AppTheme = TelerikTheme.PlatformDark;
	}
	else TelerikThemeResources.AppTheme = TelerikTheme.PlatformLight;
}
```

For more details on the `Application.RequestedTheme` property, see the <a href="https://learn.microsoft.com/en-us/dotnet/maui/user-interface/system-theme-changes?view=net-maui-8.0#detect-the-current-system-theme" target="_blank">Detect the current system theme | MS Learn</a> topic.

**3.** Switch the Telerik theme to dark or light mode&mdash;use the `Application.RequestedThemeChanged` event to detect whenever the system theme has been changed and update the Telerik resources:

```C#
public App()
{
    InitializeComponent();

    Application.Current.UserAppTheme = AppTheme.Unspecified;
    Application.Current.RequestedThemeChanged += (s, e) => ApplyTelerikTheme();
    this.ApplyTelerikTheme();
}

protected override Window CreateWindow(IActivationState? activationState)
{
    return new Window(new AppShell());
}
```

For more details on the `Application.RequestedThemeChanged` event, see the <a href="https://learn.microsoft.com/en-us/dotnet/maui/user-interface/system-theme-changes?view=net-maui-8.0#react-to-theme-changes" target="_blank">React to theme changes | MS Learn</a> topic.

## See Also

- [Telerik Themes Overview]({%slug themes-overview%})
- <a href="https://learn.microsoft.com/en-us/dotnet/maui/user-interface/system-theme-changes?view=net-maui-8.0#detect-the-current-system-theme" target="_blank">Detect the current system theme | MS Learn</a>
