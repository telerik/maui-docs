---
title: Getting Started
page_title: Getting Started with .NET MAUI Barcode Control 
description: Check our &quot;Getting Started&quot; documentation article for Telerik Barcode for .NET MAUI.
position: 1
slug: barcode-getting-started
---

# Getting Started

>important RadBarcode is rendered via the **SkiaSharp** graphics library so you need to install also `SkiaSharp.Views.Forms.Maui.Controls.Compatibility`.

## Define RadBarcode control

If your app is setup, you are ready to add a **RadBarcode** control to your page. In the sample the QRCode symbology is used, for more details on the available Barcode symbologies go to [Supported Types]({%slug barcode-supported-types-overview%}) topic.

```XAML
<telerikBarcode:RadBarcode x:Name="barcode" 
	                       Value="https://www.telerik.com/maui-ui"                               
	                       WidthRequest="100" HeightRequest="100">
    <telerikBarcode:RadBarcode.Symbology>
        <telerikBarcode:QRCode SizingMode="Stretch" />
    </telerikBarcode:RadBarcode.Symbology>
</telerikBarcode:RadBarcode>
```

In addition to this you need to add the following namespace:

```XAML
xmlns:telerikBarcode="clr-namespace:Telerik.XamarinForms.Barcode;assembly=Telerik.Maui.Controls.Compatibility"
```

Here is the result:

#### Figure 1: Barcode Getting Started

![Getting Started Example](images/barcode_getting_started.png)

## See Also

- [Key Features]({% slug barcode-key-features%})
- [Supported Barcodes]({% slug barcode-supported-types-overview%})
