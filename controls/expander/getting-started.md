---
title: Getting Started
page_title: .NET MAUI Expander Documentation - Getting Started
description: Get started with the Telerik UI for .NET MAUI Expander control and add the control to your .NET MAUI project.
position: 1
slug: expander-getting-started
---

# Getting Started with the .NET MAUI Expander

This article will guide you through the steps needed to add a basic `RadExpander` control in your application.

At the end, you will achieve the following result.

![Expander Getting Started](images/expander-getting-started.png)

## Prerequisites

Before adding the BadgeView, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

The snippet below shows a simple `RadExpander` definition in XAML:

<snippet id='expander-getting-started-xaml' />

To use the control in XAML, you need to add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

The snippet below shows a simple `RadExpander` definition in C#:
<snippet id='expander-gettingstarted-csharp' />

To use the control in C#, you need to add the following namespace:

```C#
using Telerik.Maui.Controls;
```

Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `CreateMauiApp` method of the `MauiProgram.cs` file of your project:


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

> For a runnable example with the Expander Getting Started scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **Expander > Getting Started** category.

## Additional Resources

- [.NET MAUI Expander Product Page](https://www.telerik.com/maui-ui/expander)
- [.NET MAUI Expander Forum Page](https://www.telerik.com/forums/maui?tagId=1980)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Configuration]({% slug expander-configuration %})