---
title: Getting Started
page_title: Getting Started with the RadBarcode
description: "Get started with the Telerik UI for .NET MAUI Barcode control."
position: 1
slug: barcode-getting-started
---

# Getting Started

This guide demonstrates how to add Telerik UI for .NET MAUI Barcode control to your application.

At the end, you will be able to achieve the following result.

![Getting Started Example](images/barcode_getting_started.png)

## Prerequisites

Before adding the Barcode, first you need to [setup your .NET MAUI app]({%slug maui-getting-started %}#setting-up-your-microsoft-project), and [download]({% slug maui-getting-started %}#downloading-telerik-ui-for-maui) and [install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#installing-telerik-ui-for-maui).

>important RadBarcode is rendered via the **SkiaSharp** graphics library.

## Define RadBarcode control

**1.** When the app is setup, you are ready to add a RadBarcode control to your page. The following example uses the QR Code symbology. For more details on the available Barcode symbologies, refer to the articles on the [supported 1D]({% slug 1dbarcode-overview %}) and [2D Barcode types]({% slug 2dbarcode-overview %}).

```XAML
<telerikBarcode:RadBarcode x:Name="barcode" 
	                       Value="https://www.telerik.com/maui-ui"                               
	                       WidthRequest="1000" HeightRequest="1000">
    <telerikBarcode:RadBarcode.Symbology>
        <telerikBarcode:QRCode SizingMode="Stretch" />
    </telerikBarcode:RadBarcode.Symbology>
</telerikBarcode:RadBarcode>
```

**2.** Add the following namespace:

```XAML
xmlns:telerikBarcode="clr-namespace:Telerik.XamarinForms.Barcode;assembly=Telerik.Maui.Controls.Compatibility"
```

**3.** Register the Telerik controls through `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `Configure` method of the **Startup.cs** file of your project:

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
