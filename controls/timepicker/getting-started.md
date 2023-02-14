---
title: Getting Started
page_title: .NET MAUI TimePicker Documentation - Getting Started
description: "Get started with the Telerik UI for .NET MAUI TimePicker control and add the control to your .NET MAUI project."
position: 1
previous_url: /controls/timepicker/timepicker-getting-started
slug: timepicker-getting-started
---

# Getting Started with .NET MAUI TimePicker

This guide provides the information you need to start using the Telerik UI for .NET MAUI TimePicker by adding the control to your project.

At the end, you will be able to achieve the following result.

![TimePicker Getting Started](images/timepicker_getting_started.png)

## Prerequisites

Before adding the TimePicker, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

1. When your .NET MAUI application is set up, you are ready to add a TimePicker control to your page.

 ```XAML
<telerik:RadTimePicker />
 ```
 <snippet id='timepicker-getting-started-csharp' />


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

- [.NET MAUI TimePicker product page](https://www.telerik.com/maui-ui/timepicker)
- [.NET MAUI TimePicker forum page](https://www.telerik.com/forums/maui?tagId=1850)
- [Telerik .NET MAUI blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Supported Standard Time Format Strings]({%slug timepicker-formatting%})
- [Templates]({%slug timepicker-templates%})
- [Styling]({%slug timepicker-styling%})
