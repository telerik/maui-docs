---
title: Zooming
page_title: .NET MAUI ImageEditor Documentation - Zooming
description: "Review how to set the zoom level of the images in .NET MAUI ImageEditor control."
position: 6
slug: imageeditor-zooming-image
---

# .NET MAUI ImageEditor Zooming

This article explains what are the zooming options you can apply to the image in the ImagfeEditor. The properties related to the zooming are:

* `ZoomLevel`(`double`)&mdash;Specifies the current zoom level of the viewed image. The default value is 1. A zoom level of 1 means the image is displayed with its original size. 

In addition, you can restrict the zooming by applying min and max zoom: 

* `MinZoomLevel`(`double`)&mdash;Specifies the minimum allowed zoom level of the image. The default value is 0.01. Setting the ZoomLevel property is coerced between MinZoomLevel and MaxZoomLevel.
* `MaxZoomLevel`(`double`)&mdash;Specifies the maximum allowed zoom level of the image. The default value is 10.0. Setting the ZoomLevel property is coerced between MinZoomLevel and MaxZoomLevel.


**Example with Min and Max Zoom levels**

RadImageEditor definition:

<snippet id='imageeditor-zoom-level'/>

Add the namespace used:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

 >important For the ImageEditor Zoom Level example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## See Also

- [Saving Images]({%slug imageeditor-saving-image%})
- [Loading Images]({%slug imageeditor-loading-image%})