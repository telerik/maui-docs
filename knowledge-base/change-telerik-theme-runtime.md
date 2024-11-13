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
  		<td>8.0.0</td>
  	</tr>
	</tbody>
</table>

## Description

How can I change the Telerik theme at runtime based on the device's theme and dynamically switch between dark and light modes?

## Solution

To ensure that the Telerik .NET MAUI controls respond to app theme changes correctly:

**1.** [Enable the Telerik Theming in your app]({%slug themes-overview%}#using-the-telerik-theming).

**2.** Detect the current system theme&mdash;use the `Application.RequestedTheme` property to get the current `AppTheme` and load the light or dark mode of the Telerik Theme, for example:

```C#
private void ApplyTelerikTheme()
{
    var telerikTheming = Application.Current
        .Resources
        .MergedDictionaries
        .OfType<TelerikTheming>()
        .Single();

    var swatchName = Application.Current.RequestedTheme == AppTheme.Dark ? "Purple Dark" : "Purple";
    telerikTheming.Theme = TelerikTheming.Themes
        .Single(t => t.Theme == "Telerik" && t.Swatch == swatchName);
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

    this.MainPage = new AppShell();
}
```

For more details on the `Application.RequestedThemeChanged` event, see the <a href="[https://learn.microsoft.com/en-us/dotnet/maui/user-interface/system-theme-changes?view=net-maui-8.0#detect-the-current-system-theme](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/system-theme-changes?view=net-maui-8.0#react-to-theme-changes)" target="_blank">React to theme changes | MS Learn</a> topic.

## See Also

- [Telerik Themes Overview]({%slug themes-overview%})
- <a href="https://learn.microsoft.com/en-us/dotnet/maui/user-interface/system-theme-changes?view=net-maui-8.0#detect-the-current-system-theme" target="_blank">Detect the current system theme | MS Learn</a>
