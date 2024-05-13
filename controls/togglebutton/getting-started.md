---
title: Getting Started
page_title: .NET MAUI ToggleButton Documentation - Getting Started
description: Get started with the Telerik UI for .NET MAUI ToggleButton control and add the control to your .NET MAUI project.
position: 2
slug: togglebutton-getting-started
---

# Getting Started with the .NET MAUI ToggleButton

This guide provides the information you need to start using the Telerik UI for .NET MAUI ToggleButton by adding the control to your project.

At the end, you will achieve the following result. The video is on WinUI:

![.NET MAUI ToggleButton Getting Started](images/togglebutton-getting-started.gif)

## Prerequisites

Before adding the ToggleButton, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

**1.** When your .NET MAUI application is set up, you are ready to add a ToggleButton control to your page.

<snippet id='togglebutton-gettingstarted-xaml' />
<snippet id='togglebutton-gettingstarted-csharp' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```
```C#
using Telerik.Maui.Controls;
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

>tip For a runnable example with the ToggleButton Getting Started scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **ToggleButton > Getting Started** category.

## Additional Resources

- [.NET MAUI ToggleButton Product Page](https://www.telerik.com/maui-ui/togglebutton)
- [.NET MAUI ToggleButton Forum Page](https://www.telerik.com/forums/maui?tagId=1764)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Configure the ToggleButton]({%slug togglebutton-configuration%})
- [Toggle State]({%slug togglebutton-toggle-states%})
- [Set Visual States]({%slug togglebutton-visual-states%})
- [Events]({%slug togglebutton-events%})
- [Execute Command]({%slug togglebutton-command%})
- [Style the ToggleButton]({%slug togglebutton-styling%})


