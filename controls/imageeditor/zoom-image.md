---
title: Zooming
page_title: .NET MAUI ImageEditor Documentation - Zooming
description: "Review how to set the zoom level of the images in .NET MAUI ImageEditor control."
position: 2
slug: imageeditor-zooming
---

# .NET MAUI ImageEditor Zooming

This article explains what are the zooming options you can apply to the image in the ImagfeEditor. The properties relatyed to the zooming are:

* `ZoomLevel`(`double`)&mdash;Specifies the current zoom level of the viewed image. The default value is 1. A zoom level of 1 means the image is displayed with its original size. 

In addition, you can restrict the zooming by applying min and max zoom: 

* `MinZoomLevel`(`double`)&mdash;Specifies the minimum allowed zoom level of the image. The default value is 0.01. Setting the ZoomLevel property is coerced between MinZoomLevel and MaxZoomLevel.
* `MaxZoomLevel`(`double`)&mdash;Specifies the maximum allowed zoom level of the image. The default value is 10.0. Setting the ZoomLevel property is coerced between MinZoomLevel and MaxZoomLevel.


** Example with Min and Max Zoom levels**



## See Also

- [Saving Images]({%slug imageeditor-save-image%})
- [Loading Images]({%slug imageeditor-load-image%})