---
title: Configuration
page_title: .NET MAUI SignaturePad Documentation - Configuration
description: Learn how to configure the signature's stroke color and tickness, border color and more in the Telerik UI for .NET MAUI SighnaturePad control.
position: 3
tags: sign pad, signature, maui, .net maui, sign, signature pad
slug: signaturepad-configuration
---

# .NET MAUI SignaturePad Configuration

SignaturePad for .NET MAUI provides means for customizing the appearance of the plot area as well as the signature itself. You can modify the signature stroke color and thickness.

Here is a list of the configuration properties you can apply on the SignaturePad:

* `StrokeColor`(`Color`)&mdash;Specifies the color of the signature stroke.
* `StrokeThickness`(`double`)&mdash;Defines the width of the stroke.
* `BackgroundColor`(`Color`)&mdash;Defines the background of the plot area.
* `BorderColor`(`Color`)&mdash;Defines the color of the border around the plot area.
* `CornerRadius`(`Thickness`)&mdash;Defines the corner radius around the plot area.
* `BorderThickness`(`Thickness`)&mdash;Defines the thickness of the border around the plot area.
* `Style`(`Microsoft.Maui.controls.Style`)&mdash;Defines the style applied to the SignaturePad.
* `ActualStyle`(read-only property of type`Microsoft.Maui.controls.Style`)&mdash;Gets the result from merging the `Telerik.Maui.Controls.RadSignaturePad.Style` property with the default `Microsoft.Maui.Controls.Style` of the control.

Check below a quick example on how the listed properties can be applied to a `RadSignaturePad` instance:

<snippet id='signaturepad-configuration' />

And here is the result:

![.NET MAUI SignaturePad Configuration](images/signaturepad-configuration.png)

>important For the SignaturePad Configuration example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).


## See Also

- [Events]({% slug signaturepad-events%})
- [Commands]({% slug signaturepad-commands%})
- [Saving Options]({% slug signaturepad-saving-options%})