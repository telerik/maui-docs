---
title: Getting Started
page_title: .NET MAUI CheckBox Documentation | Getting Started
description: "Get started with the Telerik UI for .NET MAUI CheckBox and add the control to your .NET MAUI project."
position: 1
slug: checkbox-getting-started
---

# Getting Started

This guide provides the information you need to start using the Telerik UI for .NET MAUI CheckBox by adding the control to your project.

At the end, you will be able to achieve the following result.

............add

## Prerequisites

Before adding the CheckBox, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

## Define the Control

1. When the your .NET MAUI application is set up, you are ready to add a CheckBox control to your page.

 ```XAML
<telerikPrimitives:RadCheckBox x:Name="checkbox" />
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.Maui.Compatibility"
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

- [Setting the Checkbox Size]({% slug checkbox-size %})
- [Defining the Checked State]({% slug checkbox-checked-states %})
- [Styling Options of the Checkbox]({% slug checkbox-styling%})
