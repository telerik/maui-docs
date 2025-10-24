---
title: Getting Started
page_title: .NET MAUI SlideView Documentation - Getting Started
description: Get started with the Telerik UI for .NET MAUI SlideView control and add the control to your .NET MAUI project.
position: 2
slug: slideview-getting-started
---

# Getting Started with .NET MAUI SlideView

This guide provides the information you need to start using Telerik UI for .NET MAUI SlideView by adding the control to your project.

At the end, you will achieve the following result.

![.NET MAUI SlideView Getting Started](images/slideview-gettingstarted.png)

## Prerequisites

Before adding SlideView to your project, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

**1.** When your .NET MAUI application is set up, you are ready to add a SlideView control to your page.

 <snippet id='slideview-getting-started-xaml' />

**2.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `CreateMauiApp` method of the `MauiProgram.cs` file of your project:

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
> For a runnable example with the SlideView Getting Started scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **SlideView > Getting Started**.

## Additional Resources

- [.NET MAUI SlideView Product Page](https://www.telerik.com/maui-ui/slideview)
- [.NET MAUI SlideView Forum Page](https://www.telerik.com/forums/maui?tagId=2058)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Binding SlideView to Data]({%slug slideview-data-binding%})
- [Using Navigation Buttons in SlideView]({%slug slideview-interaction%})
- [Executing Commands on Slide Action]({%slug slideview-commands%})
- [Handling the SlideView Events]({%slug slideview-events%})
- [Using an Item Template in SlideView]({%slug slideview-item-template%})
- [Styling the SlideView Component]({%slug slideview-navigation-buttons-styling%})
- [Styling the SlideView Indicators]({%slug indicators-styling%})