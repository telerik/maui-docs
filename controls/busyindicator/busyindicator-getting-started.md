---
title: Getting Started
page_title: Getting Started with .NET MAUI BusyIndicator control
description: Check our &quot;Getting Started&quot; documentation article for Telerik BusyIndicator for .NET MAUI control.
position: 1
slug: busyindicator-getting-started
---

# Getting Started

This guide demonstrates how to add Telerik UI for .NET MAUI BusyIndicator control to your application.

At the end, you will be able to achieve the following result.

![Getting Started Example](images/busyindicator-getting-started.png)

## Prerequisites

Before adding the BusyIndicator, first you need to [setup your .NET MAUI app]({%slug maui-getting-started %}#set-up-your-net-maui-app), and [download]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui) and [install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

>important RadBusyIndicator is rendered via the **SkiaSharp** graphics library.

## Define RadBusyIndicator control

1. When the app is setup, you are ready to add a RadBusyIndicator control to your page. The busy indicator is a layout control that can display two views depending on its current state - busy and not-busy. You can define the state of the control via its `IsBusy` property. The default value is False and the control's normal content is displayed. If you change it to True, the busy content is displayed, which by default is a spinning balls animation. Check the [Animations]({% slug busyindicator-animations %}) article to see the built-in animations, how to change them and how to us a custom animation.

 ```XAML
<telerikPrimitives:RadBusyIndicator x:Name="BusyIndicator"
									AnimationContentHeightRequest="100"
									AnimationContentWidthRequest="100"
									IsBusy="True">
	<telerikPrimitives:RadBusyIndicator.Content>
		<Label Text="This is the content of the RadBusyIndicator control displayed when the indicator is not busy."
			   TextColor="Black" />
	</telerikPrimitives:RadBusyIndicator.Content>
</telerikPrimitives:RadBusyIndicator>
 ```

2. Add the following namespace:

 ```XAML
 xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.Maui.Controls.Compatibility"
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

### See Also

- [Animations]({% slug busyindicator-animations %})
- [Custom Busy Content]({% slug busyindicator-custom-busy-content %})
