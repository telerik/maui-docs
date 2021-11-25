---
title: Getting Started
page_title: .NET MAUI Rating Documentation | Getting Started
description: "Get started with the Telerik UI for .NET MAUI Rating and add the control to your .NET MAUI project."
position: 1
slug: rating-getting-started
---

# Getting Started

This guide provides the information you need to start using the Telerik UI for .NET MAUI Barcode by adding the control to your project.

At the end, you will be able to achieve the following result.

![](images/rating-star.png)

## Prerequisites

Before adding the Rating, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

>important The Rating is rendered through the [SkiaSharp graphics library](https://skia.org/).

## Define the Control

1. When your .NET MAUI application is set up, you are ready to add a Rating control to your page.

 ```XAML
<telerikInput:RadShapeRating AutomationId="radRating"/>
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"  
 ```

1. Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `Configure` method of the `Startup.cs` file of your project:

 ```C#
 using Telerik.Maui.Controls.Compatibility;

public void Configure(IAppHostBuilder appBuilder)
{
    appBuilder        
        .UseTelerik()
        .UseMauiApp<App>();

}              
 ```

## See Also

- [Configuration of the Rating]({%slug rating-configuration%})
