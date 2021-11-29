---
title: Getting Started
page_title: .NET MAUI BusyIndicator Documentation | Getting Started
description: Check our &quot;Getting Started&quot; documentation article for Telerik BusyIndicator for .NET MAUI control.
position: 1
slug: busyindicator-getting-started
---

# Getting Started

This guide provides the information you need to start using the Telerik UI for .NET MAUI BusyIndicator by adding the control to your project.

At the end, you will be able to achieve the following result.

![Getting Started Example](images/busyindicator-getting-started.png)

## Prerequisites

Before adding the BusyIndicator, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

>important The BusyIndicator is rendered through the [SkiaSharp graphics library](https://skia.org/).

## Define the Control

1. When your .NET MAUI application is set up, you are ready to add a BusyIndicator control to your page. The BusyIndicator is a layout control that can display two views depending on its current busy or not-busy state.  

  To define the state of the control, use its `IsBusy` property. By default, `IsBusy` is set to `False` and the control displays its normal content. If you change it to `True`, the control displays its busy content, which by default, is a spinning-balls animation. Check the article on [animations]({% slug busyindicator-animations %}) to see the built-in animations, how to change them, and how to use a custom animation.

 <snippet id='busyindicator-getting-started-xaml' />

1. Add the following namespace:

 ```XAML
 xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.Maui.Controls.Compatibility"
 ```

1. Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `CreateMauiApp` method of the `MauiProgram.cs` file of your project:

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

### See Also

- [Animations]({% slug busyindicator-animations %})
- [Custom Busy Content]({% slug busyindicator-custom-busy-content %})
