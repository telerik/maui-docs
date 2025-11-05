---
title: Getting Started
page_title: Getting Started with .NET MAUI Skeleton
description: Get started with the Telerik UI for .NET MAUI Skeleton control and add the control to your .NET MAUI project.
position: 1
slug: skeleton-getting-started
---

# Getting Started with the .NET MAUI Skeleton

This guide provides the information you need to start using the Telerik UI for [.NET MAUI Skeleton]({%slug skeleton-overview%}) by adding the control to your project.

At the end, you will be able to achieve the following result.

![Telerik UI for .NET MAUI Skeleton Getting Started example](images/skeleton-getting-started.png)

## Prerequisites

Before adding the Skeleton, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

1.When your .NET MAUI application is set up, you are ready to add a Skeleton control to your page:

<snippet id='skeleton-getting-staretd-xaml' />
<snippet id='skeleton-getting-started-csharp' />

2. Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

3. Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `CreateMauiApp` method of the `MauiProgram.cs` file of your project:

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

> For a runnable example with the Skeleton Getting Started scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **Skeleton > Getting Started** category.

## Additional Resources

- [Built-in Views]({%slug skeleton-default-view%})
- [Configuration]({%slug skeleton-configuration%})
- [Animation]({%slug skeleton-animation%})
- [Custom Views]({%slug skeleton-custom-view%})
- [Styling]({%slug skeleton-styling%})

## See Also

- [.NET MAUI Skeleton Product Page](https://www.telerik.com/maui-ui/skeleton)
- [.NET MAUI Skeleton Forum Page](https://www.telerik.com/forums/maui?tagId=1764)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)