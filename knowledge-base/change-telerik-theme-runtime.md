---
title: Changing the Telerik Theme at runtime based on the device theme
page_title: Updating the Telerik Theme to a dark/light color variation when the app theme changes - .NET MAUI Knowledge Base
description: Learn how to dynamically switch the Light/Dark mode of the Telerik theme based on the target device theme
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

How can I change the Telerik theme at runtime based on the device theme (Dark/Light mode)?

## Solution

Go to the steps below to ensure the Telerik .NET MAUI controls respond to app theme changes and are properly styled whenever light/dark mode is switched.

**1.** Enable the Telerik Theming&mdash;As a first step, make sure the Telerik Theming is enabled in your app following the instructions here: [Using the Telerik Theming]({%slug theming-overview%}#using-the-telerik-theming).

**2.** Detect the current system theme&mdash;Use the `Application.RequestedTheme` property to get the current `AppTheme` and load light or dark colors of the Telerik Theming accordingly, for example:

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

For more details on the `Application.RequestedTheme` property, check [
Detect the current system theme | MS Learn](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/system-theme-changes?view=net-maui-8.0#detect-the-current-system-theme) topic.

**3.** Switch the Telerik theme for Dark/Light mode changes&mdash;Use the `Application.RequestedThemeChanged` event to detect whenever the Dark/Light system theme has been changed and update the Telerik resources:

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

For more details on the `Application.RequestedThemeChanged` event, check [
React to theme changes | MS Learn](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/system-theme-changes?view=net-maui-8.0#react-to-theme-changes) topic.

## See Also

- [Telerik Theming Overview]({%slug theming-overview%})
- [Respond to system theme changes | MS Learn](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/system-theme-changes)
