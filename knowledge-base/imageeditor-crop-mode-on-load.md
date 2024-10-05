---
title: Setting ImageEditor to Crop Mode on Image Load
description: Learn how to set the ImageEditor in .NET MAUI to automatically enter Crop mode when the image is loaded.
type: how-to
page_title: Automatically Enter Crop Mode with ImageEditor in .NET MAUI
slug: imageeditor-crop-mode-on-load
tags: imageeditor, .net maui, crop mode, image loaded
res_type: kb
---

## Environment

| Product | Version | Author |
| --- | --- | --- |
| ImageEditor for .NET MAUI | 7.1.0 | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I want the [ImageEditor]({%slug imageeditor-overview%}) for .NET MAUI to start in Crop mode when the page loads. Is this possible?

This KB article also answers the following questions:
- How to execute a command in ImageEditor when the image is loaded?
- How to programmatically apply crop operation on an image in ImageEditor?

## Solution

To make the `RadImageEditor` start in `Crop` mode when the page loads, subscribe to the `ImageLoaded` event. In the event handler, execute the `CropCommand` programmatically.

Here is how to do this:

**1.** Define the `RadImageEditor` in XAML and subscribe to the `ImageLoaded` event:

```xml
<telerik:RadImageEditor x:Name="imageEditor" 
                        Source="dotnet_bot.png"
                        ImageLoaded="OnImageLoaded"/>
```

**2.** Implement the event handler in code-behind:

```csharp
private void OnImageLoaded(object sender, Telerik.Maui.Controls.ImageEditor.ImageLoadedEventArgs e)
{
    // Apply the CropInteractiveCommand initially when the image source gets updated
    var imageSize = e.ImageSize;
    var cropCommand = this.imageEditor.CropInteractiveCommand;
    var cropCommandContext = new CropCommandContext
    {
        AspectRatio = AspectRatio.Square,
        Bounds = new Rect
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

In the above code, the `ImageLoaded` event is used to detect when an image is loaded into the ImageEditor. Upon loading, the Crop command is executed with a predefined aspect ratio, bounds, and geometry to customize the cropping area according to your requirements.

## See Also

- [ImageEditor Commands]({%slug imageeditor-commands%})
