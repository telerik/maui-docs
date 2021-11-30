---
title: Getting Started
page_title: .NET MAUI Barcode Documentation | Getting Started
description: "Get started with the Telerik UI for .NET MAUI Barcode control and add the control to your .NET MAUI project."
position: 1
slug: barcode-getting-started
---

# Getting Started

This guide provides the information you need to start using the Telerik UI for .NET MAUI Barcode by adding the control to your project.

At the end, you will be able to achieve the following result.

![Getting Started Example](images/barcode_getting_started.png)

## Prerequisites

Before adding the Barcode, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

>important The Barcode is rendered through the [SkiaSharp graphics library](https://skia.org/).

## Define the Control

1. When your .NET MAUI application is set up, you are ready to add a Barcode control to your page. The following example uses the QR Code symbology. For more details on the available Barcode symbologies, refer to the articles on the [supported 1D]({% slug 1dbarcode-overview %}) and [2D Barcode types]({% slug 2dbarcode-overview %}).

 ```XAML
<telerikBarcode:RadBarcode x:Name="barcode"
	                       Value="https://www.telerik.com/maui-ui"                               
	                       WidthRequest="1000" HeightRequest="1000">
    <telerikBarcode:RadBarcode.Symbology>
        <telerikBarcode:QRCode SizingMode="Stretch" />
    </telerikBarcode:RadBarcode.Symbology>
</telerikBarcode:RadBarcode>
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerikBarcode="clr-namespace:Telerik.XamarinForms.Barcode;assembly=Telerik.Maui.Controls.Compatibility"
 ```

1. Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `CreateMauiApp` method of the `MauiProgram.cs` file of your project:

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

## See Also

- [1D Supported Barcodes]({% slug 1dbarcode-overview %})
- [2D Supported Barcodes]({% slug 2dbarcode-overview %})
