---
title: Getting Started
page_title: Getting Started with the RadBarcode | Telerik UI for MAUI
description: "Get started with the Telerik UI for MAUI Barcode control."
position: 1
slug: barcode-getting-started
---

# Getting Started with Telerik UI for MAUI Barcode

This guide demonstrates how to add the Telerik UI for MAUI Barcode control to your project.

At the end, you will be able to achieve the following result.

![Getting Started Example](images/barcode_getting_started.png)

## Prerequisites

* Before adding the Barcode, first you need to [set up your Microsoft project]({% slug maui-getting-started %}#setting-up-your-microsoft-project), and [download]({% slug maui-getting-started %}#downloading-telerik-ui-for-maui) and [install Telerik UI for MAUI]({% slug maui-getting-started %}#installing-telerik-ui-for-maui).
* Since the RadBarcode is rendered through the [Skia 2D graphics open-source library](https://skia.org/), make sure you have it available locally.

## Defining the Barcode

1. When the project is set up, you are ready to add a RadBarcode control to your page. The following example uses the QR Code symbology. For more details on the available Barcode symbologies, refer to the articles on the [supported 1D]({% slug %}) and [2D Barcode types]({% slug %}).

		```XAML
		<telerikBarcode:RadBarcode x:Name="barcode"
			                       Value="https://www.telerik.com/maui-ui"                               
			                       WidthRequest="1000" HeightRequest="1000">
		    <telerikBarcode:RadBarcode.Symbology>
		        <telerikBarcode:QRCode SizingMode="Stretch" />
		    </telerikBarcode:RadBarcode.Symbology>
		</telerikBarcode:RadBarcode>
		```

1. Add the following namespace.

		```XAML
		xmlns:telerikBarcode="clr-namespace:Telerik.XamarinForms.Barcode;assembly=Telerik.Maui.Controls.Compatibility"
		```

1. Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method by calling it inside the `Configure` method of the `Startup.cs` file of your project.

		```C#
		using Telerik.Maui.Controls.Compatibility;

		public void Configure(IAppHostBuilder appBuilder)
		{
		    appBuilder        
		        .UseTelerik()
		        .UseMauiApp<App>();

		}              
		```

## See Also

- [1D Supported Barcodes]({% slug 1dbarcode-overview %})
- [2D Supported Barcodes]({% slug 2dbarcode-overview %})
