---
title: Display Images
page_title: .NET MAUI ImageEditor Documentation - Display Images
description: "Review the options to display images in the .NET MAUI ImageEditor control."
position: 2
slug: imageeditor-load-image
---

# Display Images in .NET MAUI ImageEdiotor

ImageEditor control enables you to visualize images using the following property:

* `Source`(of type `Microsoft.Maui.Controls.ImageSource`): Specifies the source of the image. For more details about the Source property check the [Images in .NET MAUI](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/controls/image?view=net-maui-7.0) article.

The images could be loaded from:

* `File`
* `Uri`
* `Resource`
* `Stream`

**Load images for File**


**Load images for Uri**


**Load images for Resource**


**Load images for Stream**

## Loading Template

By default a busy indicator is shown when loading an image. You can change the indicator template using the following property:

* `BusyIndicatorTemplate`(`DataTemplate`)&mdash;Defines the loading indicator when loading an image. When no template is specified, a default busy indicator is shown.


## See Also

- [Zooming Image]({%slug imageeditor-zoom-image%})
- [Saving Image]({%slug imageeditor-save-image%})