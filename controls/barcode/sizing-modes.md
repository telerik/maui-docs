---
title: Sizing Modes
page_title:  .NET MAUI Barcode Documentation - Sizing Modes
description: Learn how to define the manual, snap, or stretch sizing mode for the Telerik UI for MAUI Barcode.
position: 3
previous_url: /controls/barcode/barcode-sizing
slug: barcode-sizingmodes
---

# Sizing Modes for .NET MAUI Barcode

The Barcode provides three sizing modes that enable you to fine-tune the rendering of your codes.

* Manual&mdash;You can define the size of the smallest line or dot of the barcode through the `Module` property and, as a result, the other lines and dots multiply that size. The `Module` property is measured in device pixels.
* Snap&mdash;In the snap sizing mode the code is stretched to the available size, but each line or dot is drawn with an exact number of pixels. As a result, the lines and dots appear sharp.
* Stretch&mdash;In the stretch sizing mode, the code is stretched to fit the available size. Each line or dot size is calculated so they snap to the device pixels. for the lines to stay sharp and stretch the barcode to the available size, some of them are thicker than others.

To apply the desired sizing mode to the Barcode:

**1.** Add the sizing mode you need to the barcode, for example, the manual one.

<snippet id='barcode-features-sizingmode' />

**2.** Add the following namespace.

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

The following image shows a barcode with its applied manual sizing mode.

![Barcode SizingMode](images/barcode_sizingmode.png)

## See Also

- [1D Supported Barcodes]({% slug 1dbarcode-overview %})
- [2D Supported Barcodes]({% slug 2dbarcode-overview %})
