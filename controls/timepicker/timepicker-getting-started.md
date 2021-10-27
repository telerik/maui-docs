---
title: Getting Started
page_title: .NET MAUI TimePicker Documentation | Getting Started
description: Check our &quot;Getting Started&quot; documentation article for Telerik TimePicker for .NET MAUI.
position: 1
slug: timepicker-getting-started
---

# Getting Started

This guide demonstrates how to add Telerik UI for .NET MAUI TimePicker control to your application.

At the end, you will be able to achieve the following result:

![RadTimePicker](images/timepicker_getting_started.png)

## Prerequisites

Before adding the Time Picker, first you need to [setup your .NET MAUI app]({%slug maui-getting-started %}#set-up-your-net-maui-application), and [download]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui) and [install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

## Define RadTimePicker control

1. When the app is setup, you are ready to add a RadTimePicker control to your page:

```XAML
<telerikInput:RadTimePicker />
```
```C#
var timePicker = new RadTimePicker();
```

1. Add the following namespace:

 ```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"  
 ```

1. Register the Telerik controls through `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `Configure` method of the **Startup.cs** file of your project:

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

- [Supported Standard Time Format Strings]({%slug timepicker-formatting%})
- [Templates]({%slug timepicker-templates%})
- [Styling]({%slug timepicker-styling%})
