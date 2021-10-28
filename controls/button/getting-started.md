---
title: Getting Started
page_title: .NET MAUI Button Documentation | Getting Started
description: "Get started with the Telerik UI for .NET MAUI Button control and add the control to your .NET MAUI project."
position: 1
slug: barcode-getting-started
---

# Getting Started with the Telerik UI for .NET MAUI Button

This guide provides the information you need to start using the Telerik UI for .NET MAUI Button by adding the control to your project.

At the end, you will be able to achieve the following result.

....

## Prerequisites

Before adding the Button, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

## Define the Control

1. When the your .NET MAUI application is set up, you are ready to add a Button control to your page.

 ```XAML
<telerikInput:RadButton Text="RadButton" BackgroundColor="Transparent" BorderColor="Red" BorderThickness="2"/>
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

* [Positioning the Content of the Button]({% slug content_alignment_button %})
* [Setting the Border Thickness of Button]({% slug border_thickness_button %})
- [Creating a Circular Button]({%slug button-howto-create-circle-button%})
