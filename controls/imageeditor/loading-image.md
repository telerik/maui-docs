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

In addition, there is a `IsImageLoaded` (read-only `bool`) property that gets a value indicating whether an image is loaded in the editor.

```C#
this.imageEditor.IsImageLoaded;
```

**Here is an example how to load images from File:**

<snippet id='imageeditor-load-image-from-file'/>

**Here is an example how to load images from Uri:**

```XAML
<telerik:RadImageEditor x:Name="imageEditor" 
                        Source="https://raw.githubusercontent.com/telerik/maui-samples/main/Samples/ControlsSamples/Resources/Images/borderconfigurationavatar.png" />
        
```

**Here is an example how to load images from Stream:**

<snippet id='load-image-from-stream'/>

**Here is an example how to load images from Resources:**

<snippet id='imageeditor-toolbar-styling'/>

## Loading Template

When loading an image, the busy indicator shows by default. You can change the indicator template using the following property:

* `BusyIndicatorTemplate`(`DataTemplate`)&mdash;Defines the loading indicator when loading an image. When no template is specified, the busy indicator shows by default.

**Example with BusyTemplate**

**1.** `RadImageEditor` definition:

<snippet id='imageeditor-busy-template'/>

**2.** Add the namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

 >important For the ImageEditor Busy Template example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## Events

The ImageEditor control provides an event that is raised when an image is loaded in the editor&mdash;`ImageLoaded`.
    * The sender argument which is of type object, but can be cast to the `RadImageEditor` type.
	* An `ImageLoadedEventArgs` that provides information about an image loaded in the `RadImageEditor` control. The `ImageLoadedEventArgs` object has a reference to:
        * the `ImageSize` (`Size`). This allows you to get the size of the image in pixels.
		
### Example with ImageLoaded Event

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