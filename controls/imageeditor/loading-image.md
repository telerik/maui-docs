---
title: Display Images
page_title: .NET MAUI ImageEditor Documentation - Display Images
description: "Review the options to display images in the .NET MAUI ImageEditor control."
position: 2
slug: imageeditor-loading-image
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

```XAML
<telerik:RadImageEditor x:Name="imageEditor" 
                        Source="https://raw.githubusercontent.com/telerik/maui-samples/main/Samples/ControlsSamples/Resources/Images/borderconfigurationavatar.png" />
        
```

**Load images for Resource**



**Load images for Stream**

<snippet id='load-image-from-stream'/>

## Loading Template

By default a busy indicator is shown when loading an image. You can change the indicator template using the following property:

* `BusyIndicatorTemplate`(`DataTemplate`)&mdash;Defines the loading indicator when loading an image. When no template is specified, a default busy indicator is shown.

**Example with BusyTemplate**

RadImageEditor definition:

<snippet id='imageeditor-busy-template'/>

Add the namespace used:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## See Also

- [Zooming Image]({%slug imageeditor-zooming-image%})
- [Saving Image]({%slug imageeditor-saving-image%})