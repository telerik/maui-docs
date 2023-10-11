---
title: Getting Started
page_title: .NET MAUI RangeSlider Documentation - Getting Started
description: Get started with the Telerik UI for .NET MAUI RangeSlider and add the control to your .NET MAUI project.
position: 1
slug: rangeslider-getting-started
---

# Getting Started with the .NET MAUI RangeSlider

This guide provides the information you need to start using the Telerik UI for .NET MAUI RangeSlider by adding the control to your project.

At the end, you will achieve the following result.

![.NET MAUI RangeSlider Getting Started](images/rangeslider-getting-started.png)

## Prerequisites

Before adding the RangeSlider, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

1. [Register the Required Handlers]({%slug maui-getting-started %}#step-4-register-required-handlers).

## Define the Control

**1.** When your .NET MAUI application is setup, you are ready to add a RangeSlider control to your page. The following example demonstrates how to define the `RadRangeSlider`:

<snippet id='rangeslider-getting-started-xaml'/>
<snippet id='rangeslider-gettingstarted-csharp'/>

**2.** Add the `telerik` namespaces:

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

> For a runnable demo with the RangeSlider Getting Started example, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **RangeSlider > Getting Started** category.

## See Also

- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)