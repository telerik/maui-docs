---
title: Getting Started
page_title: .NET MAUI BottomSheet Documentation - Getting Started
description: Get started with the Telerik UI for .NET MAUI Bottom Sheet control and learn how to add the control to your .NET MAUI application.
position: 2
slug: bottomsheet-getting-started
---

# Getting Started with the .NET MAUI BottomSheet

This guide provides the information you need to start using the Telerik UI for .NET MAUI BottomSheet by adding the control to your project.

At the end, you will achieve the following result.

![BottomSheet Getting Started](images/bottomsheet-getting-started.png)

## Prerequisites

Before adding the BottomSheet, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

**1.** When the your .NET MAUI application is set up, you are ready to add the BottomSheet control to your page.

<snippet id='bottomsheet-getting-started-xaml' />
<snippet id='bottomsheet-getting-started-csharp' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```
```C#
using Telerik.Maui.Controls;
```

**3.** Add the code for opening the BottomSheet view:

<snippet id='open-bottomsheet-view' />

**4.** Add the code for closing the BottomSheet view:

<snippet id='close-bottomsheet-view' />

**5.** Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `CreateMauiApp` method of the `MauiProgram.cs` file of your project:

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

> For a runnable example with the BottomSheet Getting Started scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **BottomSheet > Getting Started**.

## Additional Resources

- [.NET MAUI BottomSheet Product Page](https://www.telerik.com/maui-ui/bottomsheet)
- [.NET MAUI BottomSheet Forum Page](https://www.telerik.com/forums/maui?tagId=1763)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Configure the BottomSheet]({%slug bottomsheet-configuration%})
- [Animation when opening and closing the bottom sheet]({%slug bottomsheet-animation%})
- [Style the BottomSheet]({%slug bottomsheet-styling%})
- [Events]({%slug bottomsheet-events%})
- [Methods]({%slug bottomsheet-methods%})
