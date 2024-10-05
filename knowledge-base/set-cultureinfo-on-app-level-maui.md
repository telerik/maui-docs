---
title: Setting the Culture Info on the App Level
description: How to override the device culture settings and apply your preferred localization settings within your Telerik UI for .NET MAUI app.
type: how-to
page_title: Setting the Culture Info on the App Level - .NET MAUI Globalization and Localization
slug: set-cultureinfo-on-app-level-maui
position: 
tags: maui, culture info, application culture, device culture, dotnet, maui
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | --- | ---- |
| 6.7.0 | Telerik UI for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |


## Description

You can override the device culture settings by explicitly setting the culture info on the app level. For example, even though the device regional and language preferences might be set to Spanish, you can choose to always apply German localization to your app instead.

## Solution

The solution applies for each platform inside the `Application/Platforms` folder:

### Android

On Android&mdash;Inside the `MainActivity` class, implement a `SetLocale()` method to change the culture info:

```C#
public class MainActivity : MauiAppCompatActivity
{
    protected override void OnCreate(Bundle? savedInstanceState)
    {
        base.OnCreate(savedInstanceState);

        this.SetLocale();

    }
    void SetLocale()
    {

        CultureInfo ci = new CultureInfo("en-US");

        Thread.CurrentThread.CurrentCulture = ci;
        Thread.CurrentThread.CurrentUICulture = ci;

        Console.WriteLine("CurrentCulture set: " + ci.Name);
    }
}
```

### iOS and MacCatalyst

On iOS or MacCatalyst&mdash;Inside the `AppDelegate.cs` file override the `FinishedLaunching` method:

```C#
public class AppDelegate : MauiUIApplicationDelegate
{
    protected override MauiApp CreateMauiApp() => MauiProgram.CreateMauiApp();

    public override bool FinishedLaunching(UIApplication application, NSDictionary launchOptions)
    {
        this.SetLocale();
        return base.FinishedLaunching(application, launchOptions);
    }

    private void SetLocale()
    {
        CultureInfo ci = new CultureInfo("en-US");

        Thread.CurrentThread.CurrentCulture = ci;
        Thread.CurrentThread.CurrentUICulture = ci;
    }
}
```

### WinUI

On WinUI&mdash;Inside the `App.xaml.cs` file, define the `CurrentCulture`:

```C#
public partial class App : MauiWinUIApplication
{
    /// <summary>
    /// Initializes the singleton application object.  This is the first line of authored code
    /// executed, and as such is the logical equivalent of main() or WinMain().
    /// </summary>
    public App()
    {
        this.InitializeComponent();
        CultureInfo.CurrentCulture = new CultureInfo("ja-JP", false);
    }

    protected override MauiApp CreateMauiApp() => MauiProgram.CreateMauiApp();
}
```

## See Also

-[Culture Info: Current UI Culture](https://learn.microsoft.com/en-us/dotnet/api/system.globalization.cultureinfo.currentuiculture?view=net-8.0)

