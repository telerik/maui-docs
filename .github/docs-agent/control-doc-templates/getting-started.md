---
title: Getting Started with the .NET MAUI {{ControlName}}
meta_title: .NET MAUI {{ControlName}} Documentation - Getting Started
description: Learn how to add the Telerik UI for .NET MAUI {{ControlName}} to your project, register the Telerik controls, and display it on a page.
position: 2
slug: {{control-slug}}-getting-started
---

# Getting Started with the .NET MAUI {{ControlName}}

This guide provides the information you need to start using the Telerik UI for [.NET MAUI {{ControlName}}]({% slug {{control-slug}}-overview %}) by adding the control to your project.

At the end, you will be able to achieve the following result.

![.NET MAUI {{ControlName}} default look after completing the getting started steps, showing {{describe the visible elements and sample data}}](images/{{control-slug}}-default-look.png)

## Prerequisites

Before adding the {{ControlName}}, complete the following steps:

1. [Set up your .NET MAUI application]({% slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

To display the {{ControlName}} on a page, complete the following steps:

1. Add the {{ControlName}} to your page:

    <snippet id='{{control-slug}}-getting-started-xaml' />

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

> For a runnable example with the {{ControlName}} Getting Started scenario, see the [SDKBrowser Demo Application]({% slug sdkbrowser-app %}) and go to the **{{ControlName}} > Getting Started** category.

## Additional Resources

- [.NET MAUI {{ControlName}} Product Page](https://www.telerik.com/maui-ui/{{product-url-segment}})
- [.NET MAUI {{ControlName}} Forum Page](https://www.telerik.com/forums/maui)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [{{Feature 1}}]({% slug {{control-slug}}-{{feature1-slug}} %})
- [Styling the {{ControlName}}]({% slug {{control-slug}}-styling %})
