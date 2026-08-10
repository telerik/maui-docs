---
title: Getting Started
page_title: .NET MAUI CircularSlider Documentation - Getting Started
description: Get started with the Telerik UI for .NET MAUI CircularSlider and add the control to your .NET MAUI project.
position: 3
slug: circularslider-getting-started
---

# Getting Started with the .NET MAUI CircularSlider

This guide provides the information you need to start using the Telerik UI for .NET MAUI CircularSlider by adding the control to your project.

At the end, you will achieve the following result.

![.NET MAUI CircularSlider Getting Started](images/circularslider-getting-started.png)

## Prerequisites

Before adding the CircularSlider, you need to:

1. [Set up your .NET MAUI application]({%slug maui-quick-start %}#prerequisites).

1. [Download Telerik UI for .NET MAUI]({%slug maui-quick-start %}#step-2-download-your-license-key-file).

1. [Install Telerik UI for .NET MAUI]({%slug maui-quick-start %}#step-3-create-a-new-maui-project).

## Define the Control

1. When your .NET MAUI application is set up, you are ready to add a CircularSlider control to your page. The following example demonstrates how to define the `RadCircularSlider`:

<snippet id='circularslider-getting-started-xaml'/>
<snippet id='circularslider-getting-started-csharp'/>

2. Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

3. Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `CreateMauiApp` method of the `MauiProgram.cs` file of your project:

```C#
using Telerik.Maui.Controls.Compatibility;

public static class MauiProgram
{
    public static MauiApp CreateMauiApp()
    {
        var builder = MauiApp.CreateBuilder();
        builder
            .UseTelerik()
            .UseMauiApp<App>()
            .ConfigureFonts(fonts =>
            {
                fonts.AddFont("OpenSans-Regular.ttf", "OpenSansRegular");
            });

        return builder.Build();
    }
}           
```

> For a runnable demo with the CircularSlider Getting Started example, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **CircularSlider > Getting Started** category.

## See Also

- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
