---
title: Getting Started
page_title: .NET MAUI SideDrawer Documentation - Getting Started
description: Learn what are the getting started steps to add the Telerik UI for .NET MAUI SideDrawer cotrol to your application.
position: 1
slug: sidedrawer-getting-started
---

# Getting Started with the .NET MAUI SideDrawer

This guide provides the information you need to start using the Telerik UI for .NET MAUI SideDrawer by adding the control to your project.

At the end, you will achieve the following result.

![.NET MAUI SideDrawer Getting Started](images/sidedrawer-gettingstarted.png)

## Prerequisites

Before adding the SideDrawer, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

The SideDrawer control contains two views - `MainContent` and `DrawerContent` The `DrawerContent` represents the hidden view (in it you can place navigational UI, any common setting, etc), while the `MainContent` hosts the main `View`.

![.NET MAUI SideDrawer Visual Structure](images/sidedrawer_visualstructure.png)

**1.** When your .NET MAUI application is set up, you are ready to add a SideDrawer control to your page. The following example demonstrates how to define the `MainContent` and `DrawerContent` of the control.

<snippet id='sidedrawer-gettingstarted-xaml'/>

**2.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
```

**3.** Add the `DefaultButtonStyle` to the `VerticalStackLayout` Resources.

```XAML
 <ResourceDictionary>
    <Style x:Key="DefaultButtonStyle" TargetType="Button">
        <Setter Property="WidthRequest" Value="180" />
        <Setter Property="HeightRequest" Value="40" />
        <Setter Property="BackgroundColor" Value="#b1b1b1" />
        <Setter Property="TextColor" Value="Black" />
    </Style>
</ResourceDictionary>
```

**4.** Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `CreateMauiApp` method of the `MauiProgram.cs` file of your project:

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
 
## Additional Resources

- [.NET MAUI SideDrawer Forum Page](https://www.telerik.com/forums/maui?tagId=1938)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Configuration]({%slug sidedrawer-features-configuration%})
- [Commands]({%slug sidedrawer-features-commands%})
- [Events]({%slug sidedrawer-features-events%})
- [Transitions]({%slug sidedrawer-features-transitions%})
