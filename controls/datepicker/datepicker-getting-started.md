---
title: Getting Started
page_title: Getting Started with .NET MAUI DatePicker Control
description: Check our &quot;Getting Started&quot; documentation article for Telerik DatePicker for .NET MAUI.
position: 1
slug: datepicker-getting-started
---

# Getting Started

This guide demonstrates how to add Telerik UI for .NET MAUI DatePicker control to your application.

At the end, you will be able to achieve the following result:

![RadDatePicker](images/datepicker_getting_started.png)

## Prerequisites

Before adding the DatePicker, first you need to [setup your .NET MAUI app]({%slug maui-getting-started %}#setup-your-net-maui-app), and [download]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui) and [install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

## Define RadDatePicker control

1. When the app is setup, you are ready to add a RadDatePicker control to your page:

 ```XAML
<telerikInput:RadDatePicker x:Name="datePicker" />
 ```

2. Add the following namespace:

 ```XAML
 xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
 ```

3. Register the Telerik controls through `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `Configure` method of the **Startup.cs** file of your project:

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

- [Formatting]({%slug datepicker-formatting%})
- [Date Range]({%slug datepicker-date-range%})
- [Templates]({%slug datepicker-templates%})
- [Selection]({%slug datepicker-selection%})
- [Styling]({%slug datepicker-styling%})
