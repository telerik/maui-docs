---
title: Value and Symbology
page_title:  .NET MAUI Barcode Documentation - Value and Symbology
description: "Learn how to set the value of the Telerik UI for .NET MAUI Barcode and control the presented data."
position: 2
previous_url: /controls/barcode/barcode-value
slug: barcode-valuesymbology
---

# Value and Symbology

Barcode exposes a `Value` property that is used to set the barcode data presented by the control. The `Value` of the barcode is of type string and the allowed length depends on the symbology you choose.

To set the symbology that will be used to convert the `Value` of the control into a visual barcode representation, use its `Symbology` property.

The most common symbologies that are supported by Barcode are:

* EAN13  
* EAN8  
* UPC-A  
* UPC-E  
* Code39  
* QRCode  
* PDF417   

For more details on the available Telerik UI for .NET MAUI Barcode symbologies, refer to the articles on [supported 1D]({% slug 1dbarcode-overview %}) and [2D Barcode types]({% slug 2dbarcode-overview %}).

To apply the desired symbology to the Barcode:

Add the symbology you need to the Barcode, for example, the Code39 one.

<snippet id='barcode-features-symbology'/>

Add the `telerik` namespace.

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

The following image shows a barcode with an applied Code39 symbology.

![Barcode Symbology](images/barcode_setsymbology_1.png)

## See Also

- [1D Supported Barcodes]({% slug 1dbarcode-overview %})
- [2D Supported Barcodes]({% slug 2dbarcode-overview %})
