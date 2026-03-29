---
title: Getting Started
page_title: .NET MAUI DropDownButton Documentation - Getting Started
description: Get started with the Telerik UI for .NET MAUI DropDownButton control and add the control to your .NET MAUI project.
position: 2
slug: dropdownbutton-getting-started
---

# Getting Started with the .NET MAUI DropDownButton

This guide provides the information you need to start using the Telerik UI for .NET MAUI DropDownButton by adding the control to your project.

At the end, you will achieve the following result.

![.NET MAUI DropDownButton Getting Started](images/dropdownbutton-getting-started.png)

## Prerequisites

Before adding the DropDownButton, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

**1.** When your .NET MAUI application is set up, you are ready to add a DropDownButton control to your page:

<snippet id='dropdownbutton-gettingstarted-xaml' />
<snippet id='dropdownbutton-gettingstarted-csharp' />

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

> For a runnable example with the DropDownButton Getting Started scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **DropDownButton > Getting Started** category.

## Additional Resources

- [Configure the DropDownButton]({%slug dropdownbutton-configuration%})
- [Loading Button]({%slug dropdownbutton-loading-button%})
- [Set Visual States]({%slug dropdownbutton-visual-states%})
- [Events]({%slug dropdownbutton-events%})
- [Execute Command]({%slug dropdownbutton-command%})
- [Style the DropDownButton]({%slug dropdownbutton-styling%})

## See Also

- [.NET MAUI DropDownButton Product Page](https://www.telerik.com/maui-ui/dropdownbutton)
- [.NET MAUI DropDownButton Forum Page](https://www.telerik.com/forums/maui?tagId=1764)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)