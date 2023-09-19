---
title: Display Images
page_title: .NET MAUI ImageEditor Documentation - Display Images
description: Learn what are the options to display images in the Telerik UI for .NET MAUI ImageEditor control.
position: 2
slug: imageeditor-loading-image
---

# Display Images in the .NET MAUI ImageEditor

The ImageEditor control enables you to visualize images by using the following property:

* `Source`(of type `Microsoft.Maui.Controls.ImageSource`)—Specifies the source of the image. For more details about the `Source`` property, check the [Images in .NET MAUI](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/controls/image?view=net-maui-7.0) article.

In addition, by using the `IsImageLoaded` (read-only `bool`) property, you can get information whether an image is loaded in the editor. There are many scenarios this property helps. For example, if you want to apply a crop operation as soon as the image is loaded.

    ```C#
    this.imageEditor.IsImageLoaded;
    ```
The ImageEditor can load images from the following sources:

* `File`
* `Uri`
* `Stream`
* `Resources`

The examples below demonstrate how to load images from the four different sources.

>caption Loading images from a file

<snippet id='imageeditor-load-image-from-file'/>

>caption Loading images from a URI

```XAML
<telerik:RadImageEditor x:Name="imageEditor" 
                        Source="https://raw.githubusercontent.com/telerik/maui-samples/main/Samples/ControlsSamples/Resources/Images/borderconfigurationavatar.png" />
```

>caption Loading images from a stream

<snippet id='load-image-from-stream'/>

>caption Loading images from a resource

<snippet id='imageeditor-toolbar-styling'/>

## Loading Template

When loading an image, the busy indicator shows by default. You can change the indicator template using the following property:

* `BusyIndicatorTemplate`(`DataTemplate`)&mdash;Defines the loading indicator when loading an image. When no template is specified, the busy indicator shows by default.

The following example demonstrates how to use the `BusyIndicatorTemplate`.

**1.** Add the `RadImageEditor` definition:

<snippet id='imageeditor-busy-template'/>

**2.** Add the namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

> For a runnable example demonstrating the ImageEditor Busy Template, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## Events

The ImageEditor control provides the `ImageLoaded` event that is raised when an image is loaded in the editor. The event handler receives the following parameters:

* The `sender` argument which is of type object, but can be cast to the `RadImageEditor` type.
* An `ImageLoadedEventArgs` that provides information about an image loaded in the `RadImageEditor` control. The `ImageLoadedEventArgs` object has a reference to the `ImageSize` (`Size`). This allows you to get the size of the image in pixels.

The following example demonstrates how to use the `ImageLoaded` event.

**1.** Add the `RadImageEditor` definition:

```XAML
<telerik:RadImageEditor x:Name="imageEditor" ImageLoaded="OnImageLoaded"/>
```

**2** The `ImageLoaded` event handler implementation. Execute `CropInteractiveCommand` with custom crop bounds that are calculated based on the image's size:

```C#
private void OnImageLoaded(object sender, ImageLoadedEventArgs eventArgs)
{
    var imageSize = eventArgs.ImageSize;
    var cropCommand = this.imageEditor.CropInteractiveCommand;
    var cropCommandContext = new CropCommandContext
    {
        AspectRatio = AspectRatio.Square,
        Bounds = new Rectangle
        {
            X = imageSize.Width * 0.25,
            Y = imageSize.Height * 0.25,
            Width = imageSize.Width * 0.5,
            Height = imageSize.Height * 0.5
        },
        Geometry = new RadEllipseGeometry
        {
            Center = new Point(0.5, 0.5),
            Radius = new Size(0.5, 0.5)
        }
    };

    if (cropCommand.CanExecute(cropCommandContext))
    {
        cropCommand.Execute(cropCommandContext);
    }
}
```

## See Also

- [Zooming Image]({%slug imageeditor-zooming-image%})
- [Saving Image]({%slug imageeditor-saving-image%})
