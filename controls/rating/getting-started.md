---
title: Getting Started
page_title: .NET MAUI Rating Documentation - Getting Started
description: "Get started with the Telerik UI for .NET MAUI Rating and add the control to your .NET MAUI project."
position: 1
previous_url: /controls/rating/rating-getting-started
slug: rating-getting-started
---

# Getting Started with the .NET MAUI Rating

This guide provides the information you need to start using the Telerik UI for .NET MAUI Rating by adding the control to your project.

At the end, you will be able to achieve the following result.

![Rating Getting Started](images/rating-star.png)

## Prerequisites

Before adding the Rating, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

>important The Rating is rendered through the [SkiaSharp graphics library](https://skia.org/).

## Define the Control

1. When your .NET MAUI application is set up, you are ready to add a Rating control to your page.

 <snippet id='rating-gettingstarted-xaml' />

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

- [.NET MAUI Rating Product Page](https://www.telerik.com/maui-ui/rating)
- [.NET MAUI Rating Forum Page](https://www.telerik.com/forums/maui?tagId=1857)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Configuration of the Rating]({%slug rating-configuration%})
