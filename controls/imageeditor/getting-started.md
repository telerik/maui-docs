---
title: Getting Started
page_title: .NET MAUI ImageEditor Documentation - Getting Started
description: "Get started with the Telerik UI for .NET MAUI ImageEditor and add the control to your .NET MAUI project."
position: 1
slug: imageeditor-getting-started
---

# Getting Started with .NET MAUI ImageEditor control

This guide provides the information you need to start using the Telerik UI for .NET MAUI ImageEditor by adding the control to your project.

At the end, you will be able to achieve the following result.

![ImageEditor Getting Started](images/imageEditor-gettingstarted.png)

## Prerequisites

Before adding the ImageEditor, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

>important The ImageEditor is rendered through the [SkiaSharp graphics library](https://skia.org/).

## Define the Control

1. When the your .NET MAUI application is set up, you are ready to add an ImageEditor control to your page.

 <snippet id='imageeditor-getting-started-xaml'/>
 <snippet id='imageeditor-getting-started-csharp'/>

**1.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**2.** For the demo the image is loaded in the ImageEditor for a `stream`:

<snippet id='load-image-from-stream'/>

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
 >important For the ImageEditor Getting Started example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## Additional Resources

- [.NET ImageEditor page](https://www.telerik.com/maui-ui/imageeditor)
- [.NET MAUI ImageEditor forum page](https://www.telerik.com/forums/maui?tagId=1781)
- [Telerik .NET MAUI blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Saving Images]({%slug imageeditor-saving-image%})
- [Loading Images]({%slug imageeditor-loading-image%})
- [Zooming Images]({%slug imageeditor-zooming-image%})
