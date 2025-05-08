---
title: Saving Images
page_title: .NET MAUI ImageEditor Documentation - Saving Images
description: Learn what are the Saving Options in the Telerik UI for .NET MAUI ImageEditor control provides.
position: 5
slug: imageeditor-saving-image
---

# Saving Images with .NET MAUI ImageEditor

`RadImageEditor` control gives you the option to save the currently edited image using the `SaveAsync` method. The `SaveAsync` method has the following overloads:

* `SaveAsync(Stream outputStream, ImageFormat imageFormat, double imageQuality)`
Saves the currently edited image to the specified stream, encoding it with the given format and quality.

* `SaveAsync(Stream outputStream, ImageFormat imageFormat, double imageQuality, Size maximumSize)`
Saves the currently edited image to the specified stream, encoding it with the given format, quality and size.

* `SaveAsync(Stream outputStream, ImageFormat imageFormat, double imageQuality, double scaleFactor)`
Saves the currently edited image to the specified stream, encoding it with the given format, quality and scale.

where:

* `outputStream`(`Stream`)&mdash;Specifies the output stream to save the image to.
* `imageFormat`(`ImageFormat`)&mdash;Specifies the image format to encode the image to. The available options from ImageFormat enumeration are JPEG, PNG, GIF and BMP. Currently, **Tif** is not supported.
* `imageQuality`(`double`)&mdash;Specifies the image quality to save the image to. The range is between 1 and 0, where the value of 1 specifies the maximum possible quality, resulting in minimum compression and the value of 0 specifies the minimum possible quality, resulting in maximum compression.
* `maximumSize`(`Size`)&mdash;Specifies the maximum size to save the image to. If the original image size is larger than the maximum size, the `SaveAsync` will save the image in the submitted maximum Size but the aspect ratio will be kept.
* `scaleFactor`(`double`)&mdash;Specifies a scale factor, which can be used to reduce the size of the final image. For example when setting values below 1 downscale the image before saving, which reducing the final image size and values above 1 upscale the image before saving, which increasing the final image size.

>note The saved image contains all currently applied changes in the ImageEditor.

**Example for Saving Images**

Here is how the `RadImageEditor` is defined:

<snippet id='imageeditor-save-image'/>

* This example shows how to save image with the original size:

<snippet id='imageeditor-saveimage-original'/>

![Toolbar Visual Structure](images/imageeditor-saving-originalsize.png "Visual elements of Toolbar")

* This example shows how to save image with the specific size:

<snippet id='imageeditor-saveimage-specific-size'/>

* This example shows how to save image with downscale size:

<snippet id='imageeditor-saveimage-downscaled'/>

 >important For the ImageEditor Save Image example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## See Also

- [Zooming Image]({%slug imageeditor-zooming-image%})
- [Loading Image]({%slug imageeditor-loading-image%})