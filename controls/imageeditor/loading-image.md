---
title: Display Images
page_title: .NET MAUI ImageEditor Documentation - Display Images
description: Learn what are the options to display images in the Telerik UI for .NET MAUI ImageEditor control.
position: 2
slug: imageeditor-loading-image
---

# Display Images in .NET MAUI ImageEditor

ImageEditor control enables you to visualize images using the following property:

* `Source`(of type `Microsoft.Maui.Controls.ImageSource`): Specifies the source of the image. For more details about the Source property check the [Images in .NET MAUI](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/controls/image?view=net-maui-7.0) article.

The images can be loaded from:

* `File`
* `Uri`
* `Stream`
* `Resources`

**Load Images for File**

<snippet id='imageeditor-load-image-from-file'/>

**Load Images for Uri**

```XAML
<telerik:RadImageEditor x:Name="imageEditor" 
                        Source="https://raw.githubusercontent.com/telerik/maui-samples/main/Samples/ControlsSamples/Resources/Images/borderconfigurationavatar.png" />
        
```

**Load Images for Stream**

<snippet id='load-image-from-stream'/>

**Load Images for Resources**

<snippet id='imageeditor-toolbar-styling'/>

## Loading Template

By default a busy indicator is illustrated when loading an image. You can change the indicator template using the following property:

* `BusyIndicatorTemplate`(`DataTemplate`)&mdash;Defines the loading indicator when loading an image. When no template is specified, a default busy indicator is illustrated.

**Example with BusyTemplate**

`RadImageEditor` definition:

<snippet id='imageeditor-busy-template'/>

Add the namespace used:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

 >important For the ImageEditor Busy Template example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## See Also

- [Zooming Image]({%slug imageeditor-zooming-image%})
- [Saving Image]({%slug imageeditor-saving-image%})