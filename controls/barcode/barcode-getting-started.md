---
title: Getting Started
page_title: Getting Started with .NET MAUI Barcode Control 
description: Check our &quot;Getting Started&quot; documentation article for Telerik Barcode for .NET MAUI.
position: 1
slug: barcode-getting-started
---

# Getting Started

>important RadBarcode is rendered via the **SkiaSharp** graphics library.

## Define RadBarcode control

If your app is setup, you are ready to add a **RadBarcode** control to your page. In the sample the QRCode symbology is used, for more details on the available Barcode symbologies go to [Supported Types]({%slug barcode-supported-types-overview%}) topic.

```XAML
<telerikBarcode:RadBarcode x:Name="barcode" 
	                       Value="https://www.telerik.com/maui-ui"                               
	                       WidthRequest="1000" HeightRequest="1000">
    <telerikBarcode:RadBarcode.Symbology>
        <telerikBarcode:QRCode SizingMode="Stretch" />
    </telerikBarcode:RadBarcode.Symbology>
</telerikBarcode:RadBarcode>
```

Add the following namespace:

```XAML
xmlns:telerikBarcode="clr-namespace:Telerik.XamarinForms.Barcode;assembly=Telerik.Maui.Controls.Compatibility"
```

Register the Telerik controls through `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `Configure` method of the **Startup.cs** file of your project:

```C#
using Telerik.Maui.Controls.Compatibility;

 

public void Configure(IAppHostBuilder appBuilder)
{
    appBuilder        
        .UseTelerik()
        .UseMauiApp<App>();
        
}              
```

Here is the result:

![Getting Started Example](images/barcode_getting_started.png)

## See Also

- [Key Features]({% slug barcode-key-features%})
- [Supported Barcodes]({% slug barcode-supported-types-overview%})
