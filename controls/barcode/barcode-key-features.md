---
title: Key Features
page_title: .NET MAUI Barcode Documentation | Key Features
description: Check our &quot;Key Features&quot; documentation article for Telerik Barcode for .NET MAUI.
position: 2
slug: barcode-key-features
---

# Key Features

The purpose of this help article is to show you the key features of the **RadBarcode** control. 

## Setting barcode value

RadBarcode exposes a **Value** property that is used to set the barcode data presented by the control. The **Value** of the barcode is of type string and the allowed length depends on the symbology you choose.

## Setting the symbology

Through the **Symbology** property you could set the symbology that will be used to convert the Value of the control into a visual barcode representation.  RadBarcode supports the most commonly used symbologies such as:

* EAN13  
* EAN8  
* UPC-A  
* UPC-E  
* Code39  
* QRCode  
* PDF417   

>For more details on the available symbologies go to [Supported Types]({%slug barcode-supported-types-overview %}) topic.

Here is a quick example of RadBarcode with the Code39 symbology applied:

```XAML
<telerikBarcode:RadBarcode WidthRequest="200" HeightRequest="100" 
        HorizontalOptions="Center" VerticalOptions="Center"
        Value="58000106">
    <telerikBarcode:RadBarcode.Symbology>
        <telerikBarcode:Code39 HorizontalTextAlignment="Center"
                          SizingMode="Stretch" 
                          ShowText="True"  
                          CodeTextSpacing="10"/>
    </telerikBarcode:RadBarcode.Symbology>
</telerikBarcode:RadBarcode>
```

Add the following namespace:

```XAML
xmlns:telerikBarcode="clr-namespace:Telerik.XamarinForms.Barcode;assembly=Telerik.Maui.Controls.Compatibility"
```

#### Figure 1:  RadBarcode with 1D Code39 symbology

![Barcode Symbology](images/barcode_setsymbology_1.png)
	
## Defining the sizing mode

RadBarcode provides three sizing modes that will help you fine-tune the rendering of your codes:

* Manual – you could define the size of the smallest line or dot of the code through the Module property and the other lines and dots multiply that size. Module property is measured in device pixels;
* Snap – the code is stretched to the available size, but each line or dot is drawn with exact number of pixels so they look sharp;
* Stretch – the code is stretched in such a way to fit exactly the available size, each line or dot size is calculated so they snap to the device pixels. In order the lines to stay sharp and stretch the barcode to the available size, some of them are slightly thicker than others.

The next example shows the same Barcode with Manual SizingMode:

```XAML
<telerikBarcode:RadBarcode WidthRequest="300" HeightRequest="100" 
        HorizontalOptions="Center" VerticalOptions="Center"
        Value="58000106">
    <telerikBarcode:RadBarcode.Symbology>
        <telerikBarcode:Code39 HorizontalTextAlignment="Center" 
                          SizingMode="Manual"
                          Module="2" 
                          ShowText="True"  
                          CodeTextSpacing="10"/>
    </telerikBarcode:RadBarcode.Symbology>
</telerikBarcode:RadBarcode>
```

Add the following namespace:

```XAML
xmlns:telerikBarcode="clr-namespace:Telerik.XamarinForms.Barcode;assembly=Telerik.Maui.Controls.Compatibility"
```

And here is the result:

#### Figure 2: Barcode with Manual SizingMode

![Barcode SizingMode](images/barcode_sizingmode.png)

## Setting AutoCheckSum

By default, RadBarcode control automatically adds a checksum at the end of the barcode. You could disable this by setting **AutoCheckSum** property of its Symbology to false.  

>If you disable the AutoCheckSum feature, you would need to manually add a checksum to ensure the reliability of the barcode symbol.

## Changing the colors

You could easily change the visual appearance of your Barcodes in order to match your application theme through **ForegroundColor** and **BackgroundColor** properties.

```XAML
<telerikBarcode:RadBarcode WidthRequest="200" HeightRequest="100" 
        HorizontalOptions="Center" VerticalOptions="Center" 
        ForegroundColor="DarkBlue"
        BackgroundColor="Beige"
        Value="58000106">
    <telerikBarcode:RadBarcode.Symbology>
        <telerikBarcode:Code39 SizingMode="Stretch" />
    </telerikBarcode:RadBarcode.Symbology>
</telerikBarcode:RadBarcode>
```

Add the following namespace:

```XAML
xmlns:telerikBarcode="clr-namespace:Telerik.XamarinForms.Barcode;assembly=Telerik.Maui.Controls.Compatibility"
```
	
#### Figure 3: Barcode with customized colors

![Barcode Colors](images/barcode_colors.png)

## See Also

- [Supported Types]({%slug barcode-supported-types-overview %})
