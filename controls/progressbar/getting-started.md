---
title: Getting Started
page_title: .NET MAUI ProgressBar Documentation - Getting Started
description: Get started with the Telerik UI for .NET MAUI ProgressBar control and add the control to your .NET MAUI project.
position: 2
slug: progressbar-getting-started
---

# Getting Started with the .NET MAUI ProgressBar control

This guide provides the information you need to start using the Telerik UI for .NET MAUI ProgressBar by adding the control to your project.

At the end, you will achieve the following result.

![.NET MAUI ProgressBar Getting Started](images/progressbar-getting-started.png)

## Prerequisites

Before adding the Barcode, you need to:

1. [Set up your .NET MAUI application]({%slug maui-quick-start %}#prerequisites).

1. [Download Telerik UI for .NET MAUI]({%slug maui-quick-start %}#step-2-download-your-license-key-file).

1. [Install Telerik UI for .NET MAUI]({%slug maui-quick-start %}#step-3-create-a-new-maui-project).

## Define the Control in XAML or C#.

**1.** The snippet below shows a simple `RadLinearProgressBar` definition.

<snippet id='progressbar-getting-started-xaml'/>
<snippet id='progressbar-getting-started-csharp'/>

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

>important For the ProgressBar Getting Started example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## Additional Resources

- [.NET MAUI ProgressBar Product Page](https://www.telerik.com/maui-ui/progressbar)
- [.NET MAUI ProgressBar Forum Page](https://www.telerik.com/forums/maui?tagId=1978)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Configuration]({%slug progressbar-configuration%})
- [Animations]({%slug progressbar-animations%})
- [Indeterminate Mode]({%slug progressbar-indeterminate-mode%})
- [Events]({%slug progressbar-events%})
- [Styling]({%slug progressbar-styling%})
