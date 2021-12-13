---
title: Getting Started
page_title: .NET MAUI Path Documentation | Getting Started
description: "Get started with the Telerik UI for .NET MAUI Path and add the control to your .NET MAUI project."
position: 1
slug: path-getting-started
---

# Getting Started

This guide provides the information you need to start using the Telerik UI for .NET MAUI Path by adding the control to your project.

At the end, you will be able to achieve the following result.

...

## Prerequisites

Before adding the Path, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

>important The Path is rendered through the [SkiaSharp graphics library](https://skia.org/).

## Define the Control

1. When your .NET MAUI application is set up, you are ready to add a Path control to your page. The Path exposes the `Geometry` property, which you have to assign to a `RadPathGeometry` object. The [`RadPathGeometry`]({% slug path-structure %}) object consists of different Path figures such as lines and arcs.

  For demonstration purposes, let's choose one of the built-in geometries the Path supports, for example, the star pattern, and set it directly to the `Geometry` property:

 ```XAML
<telerikPrimitives:RadPath x:Name="starPath"
                           StrokeThickness="0"
                           Fill="#FFC325"
                           Geometry="{x:Static telerikInput:Geometries.Star}" />
 ```

1. Add the following namespaces:

 ```XAML
xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.Maui.Controls.Compatibility"
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
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

## See Also

- [Path Geometry]({% slug path-structure %})
- [Geometry Types]({% slug geometry-types %})
