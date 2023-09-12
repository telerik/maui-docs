---
title: Getting Started
page_title: .NET MAUI Border Documentation | Getting Started
description: Get started with the Telerik UI for .NET MAUI Border control and learn how to add the control to your .NET MAUI application.
position: 10
previous_url: /controls/border/border-getting-started
slug: border-getting-started
---

# Getting Started with the .NET MAUI Border

This guide provides the information you need to start using the Telerik UI for .NET MAUI Border by adding the control to your project.

At the end, you will achieve the following result.

![Border Getting Started](images/border-getting-started.png)

## Prerequisites

Before adding the Border, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

**1.** When the your .NET MAUI application is set up, you are ready to add the Border control to your page by using its definition in XAML.

<snippet id='border-getting-started-xaml' />

**2.** Add the `telerik` namespace:

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

> For a runnable example with the Border Getting Started scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **Border > Getting Started**.

## Additional Resources

- [.NET MAUI Border Product Page](https://www.telerik.com/maui-ui/border)
- [.NET MAUI Border Forum Page](https://www.telerik.com/forums/maui?tagId=1763)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Setting the Color of the Border]({%slug border-styling %}#border-color)
- [Setting the Border Thickness]({% slug border-styling%}#border-thickness)
- [Configuring the Corner Radius of the Border]({% slug border-corner-radius %})
