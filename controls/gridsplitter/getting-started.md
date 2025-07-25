---
title: Getting Started
page_title: .NET MAUI GridSplitter Documentation - Getting Started
description: Get started with the Telerik UI for .NET MAUI GridSplitter and add the control to your .NET MAUI project.
position: 2
slug: gridsplitter-getting-started
---

# Getting Started with the .NET MAUI GridSplitter

This guide provides the information you need to start using the Telerik UI for .NET MAUI GridSplitter by adding the control to your project.

At the end, you will achieve the following result.

![.NET MAUI GridSplitter Getting Started](images/gridplitter-getting-started.gif)

## Prerequisites

Before adding the GridSplitter, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

**1.** When your .NET MAUI application is set up, you are ready to add a GridSplitter control to your page.

<snippet id='gridsplitter-getting-started' />

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

> For a runnable example with the GridSplitter Getting Started scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **GridSplitter > Getting Started** category.

## Additional Resources

- [.NET MAUI GridSplitter Product Page](https://www.telerik.com/maui-ui/gridsplitter)
- [.NET MAUI GridSplitter Forum Page](https://www.telerik.com/forums/maui?tagId=1784)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Configure the GridSplitter]({%slug gridsplitter-configuration%})
- [Styling the GridSplitter]({%slug gridsplitter-styling%})
