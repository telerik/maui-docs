---
title: Getting Started
page_title: Getting Started with .NET MAUI PieChart
description: Get started with the Telerik UI for .NET MAUI PieChart and add the control to your .NET MAUI project.
components: ["charts"]
tags: charts, pie chart, getting started, .net maui, ui for .net maui
position: 2
slug: charts-pie-getting-started
---

# Getting Started with the .NET MAUI PieChart

This guide provides the information you need to start using the Telerik UI for [.NET MAUI PieChart]({% slug charts-pie-overview %}) by adding the control to your project.

At the end, you will be able to achieve the following result.

![Telerik UI for .NET MAUI PieChart default view showing a four-slice pie chart](images/charts-pie-getting-started.png)

## Prerequisites

Before adding the Pie Chart, you need to:

1. [Set up your .NET MAUI application]({% slug maui-quick-start %}#prerequisites).

1. [Set Up Telerik Development Environment]({%slug maui-quick-start %}#set-up-telerik-development-environment)

## Define the Control

1. When your .NET MAUI application is set up, you are ready to add a `RadPieChart` to your page. The following example defines a chart with a `PieSeries`:

    <snippet id='chart-pie-getting-started-xaml' />

2. Add the `charts` namespace:

    ```XAML
    xmlns:charts="clr-namespace:Telerik.Maui.Controls.Charts;assembly=Telerik.Maui.Controls"
    ```

3. Add sample data to the `PieSeries`:

    <snippet id='chart-datamodel-piedata' />

4. Define the `ViewModel`:

    <snippet id='chart-pie-viewmodel' />

5. Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `CreateMauiApp` method of the `MauiProgram.cs` file of your project:

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

The `PieSeries` binds to a collection of items through its `ItemsSource` property, while the `ValueBinding` and `LabelBinding` properties define which data-item members supply the value and the label of each slice.

> For a runnable example with the Pie Chart Getting Started scenario, go to the [SDKBrowser Demo Application]({% slug sdkbrowser-app %}) and navigate to the **Charts > Getting Started** category.

## Additional Resources

- [.NET MAUI Pie Chart Series]({% slug charts-pie-series %})
- [.NET MAUI Charts Product Page](https://www.telerik.com/maui-ui/charts)
- [.NET MAUI Charts Forum Page](https://www.telerik.com/forums/maui)

## See Also

- [Pie Chart Series]({% slug charts-pie-series %})
- [Pie Chart Visual Structure]({% slug charts-pie-visual-structure %})
