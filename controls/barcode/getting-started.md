---
title: Getting Started
page_title: .NET MAUI Barcode Documentation - Getting Started
description: Get started with the Telerik UI for .NET MAUI Barcode control and add the control to your .NET MAUI project.
position: 1
previous_url: /controls/barcode/barcode-getting-started
slug: barcode-getting-started
---

# Getting Started with the .NET MAUI Barcode

This guide provides the information you need to start using the Telerik UI for .NET MAUI Barcode by adding the control to your project.

At the end, you will achieve the following result.

![Barcode Getting Started](images/barcode_getting_started.png)

## Prerequisites

Before adding the Barcode, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

>important The Barcode is rendered through the [SkiaSharp graphics library](https://skia.org/).

## Define the Control

**1.** When your .NET MAUI application is set up, you are ready to add a Barcode control to your page. The following example uses the QR Code symbology. For more details on the available Barcode symbologies, refer to the articles on the [supported 1D]({% slug 1dbarcode-overview %}) and [2D Barcode types]({% slug 2dbarcode-overview %}).

<snippet id='barcode-gettingstarted' />

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

> For a runnable example with the Barcode Getting Started scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **Barcode > Getting Started**.

## Additional Resources

- [.NET MAUI Barcode Product Page](https://www.telerik.com/maui-ui/barcode)
- [.NET MAUI Barcode Forum Page](https://www.telerik.com/forums/maui?tagId=1780)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [1D Supported Barcodes]({% slug 1dbarcode-overview %})
- [2D Supported Barcodes]({% slug 2dbarcode-overview %})
