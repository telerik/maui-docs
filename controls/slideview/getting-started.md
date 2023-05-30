---
title: Getting Started
page_title: .NET MAUI SlideView Documentation - Getting Started
description: "Get started with the Telerik UI for .NET MAUI SlideView control and add the control to your .NET MAUI project."
position: 1
slug: slideview-getting-started
---

# Getting Started with .NET MAUI SlideView

This guide provides the information you need to start using the Telerik UI for .NET MAUI SlideView by adding the control to your project.

Before adding the SlideView, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

1. When your .NET MAUI application is set up, you are ready to add a SlideView control to your page.

 <snippet id='slideview-getting-started-xaml' />

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

- [Telerik .NET MAUI blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Data Binding]({%slug slideview-data-binding%})
- [Interaction ]({%slug slideview-interaction%})
- [Commands ]({%slug slideview-commands%})
- [Events ]({%slug slideview-events%})
- [Item Template]({%slug slideview-item-template%})
- [Control Template]({%slug slideview-control-template%})
- [SlideView Styling ]({%slug slideview-styling%})
- [Indicators Styling]({%slug indicators-styling%})