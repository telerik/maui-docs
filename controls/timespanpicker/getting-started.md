---
title: Getting Started
page_title:  .NET MAUI TimeSpanPicker Documentation - Getting Started
description: "Get started with the Telerik UI for .NET MAUI TimeSpanPicker and add the control to your .NET MAUI project."
position: 1
previous_url: /controls/timespanpicker/timespanpicker-getting-started
slug: timespanpicker-getting-started
---

# Getting Started with .NET MAUI TimeSpanPicker

This guide provides the information you need to start using the Telerik UI for .NET MAUI TimeSpanPicker by adding the control to your project.

At the end, you will be able to achieve the following result.

![TimeSpan Picker Getting Started](images/timespanpicker_getting_started.png)

## Prerequisites

Before adding the TimeSpanPicker, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

1. When your .NET MAUI application is set up, you are ready to add a TimeSpanPicker control to your page.

 ```XAML
<telerik:RadTimeSpanPicker />
 ```
 ```C#
var timeSpanPicker = new RadTimeSpanPicker();
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
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

## Additional Resources

- [.NET MAUI TimeSpanPicker product page](https://www.telerik.com/maui-ui/timespanpicker)
- [.NET MAUI TimeSpanPicker forum page](https://www.telerik.com/forums/maui?tagId=1851)
- [Telerik .NET MAUI blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Suppoted Standard TimeSpan Format Strings]({%slug timespanpicker-formatting%})
- [Templates]({%slug timespanpicker-templates%})
- [Styling]({%slug timespanpicker-styling%})
