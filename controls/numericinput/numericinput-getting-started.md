---
title: Getting Started
page_title: Getting Started with .NET MAUI NumericInput Control
description: "Get started with the Telerik UI for .NET MAUI NumericInput and add the control to your .NET MAUI project."
position: 1
slug: numericinput-getting-started
---

# Getting Started

This guide provides the information you need to start using the Telerik UI for .NET MAUI NumericInput by adding the control to your project.

At the end, you will be able to achieve the following result.

![NumericInput Getting Started Example](images/numericinput-getting-started.png)

For more examples on the NumericInput main features, refer to the [SDK Browser MAUI application]({% slug maui-demo-app %}).

## Prerequisites

Before adding the NumericInput, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

## Define the Control

1. When your .NET MAUI application is set up, you are ready to add a NumericInput control to your page.

 ```XAML
<telerikInput:RadNumericInput x:Name="numericInput" />
 ```

1. Add the following namespace:

 ```XAML
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

- [Globalization]({%slug numericinput-globalization%})
- [Commands]({%slug numericinput-commands%})
