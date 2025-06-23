---
title: Correcting Upside Down Image Display in ImageEditor for .NET MAUI
description: Resolve the issue of upside-down image display in ImageEditor for .NET MAUI on iOS by handling EXIF metadata.
type: how-to
page_title: Fixing Upside Down Image in ImageEditor for .NET MAUI on iOS
meta_title: Fixing Upside Down Image in ImageEditor for .NET MAUI on iOS
slug: correcting-upside-down-image-imageeditor-dotnet-maui
tags: imageeditor,.net maui,ios,skia,exif,bitmap,image-orientation,image-metadata
res_type: kb
ticketid: 1691149
---

## Environment

<table>
<tbody>
<tr>
<td> Product </td>
<td> ImageEditor for .NET MAUI </td>
</tr>
<tr>
<td> Version </td>
<td> 11.0.0 </td>
</tr>
</tbody>
</table>

## Description

Images loaded into the [ImageEditor](https://docs.telerik.com/devtools/maui/controls/imageeditor/overview) for .NET MAUI on iOS may appear upside down due to how SkiaSharp handles EXIF metadata. This metadata instructs the renderer to apply a specific rotation to the image, causing the display issue.

This knowledge base article also answers the following questions:
- How to fix upside-down images in ImageEditor for .NET MAUI?
- Why are images rotated incorrectly in ImageEditor on iOS?
- How to handle EXIF metadata for ImageEditor in .NET MAUI?

## Solution

To ensure proper image orientation, handle EXIF metadata before loading the image into the ImageEditor.

### Steps to Correct Image Orientation

1. **Add Helper Methods**  
   Implement the following methods to handle image loading and orientation:

      ```csharp
      public SKBitmap LoadBitmapWithOrigin(Stream imageStream, out SKEncodedOrigin origin)
      {
          if (imageStream.CanSeek)
              imageStream.Seek(0, SeekOrigin.Begin);
      
          using (var codec = SKCodec.Create(imageStream))
          {
              if (codec == null)
              {
                  origin = SKEncodedOrigin.Default; 
                  return null;
              }
      
              origin = codec.EncodedOrigin;
              var info = new SKImageInfo(codec.Info.Width, codec.Info.Height);
              var bitmap = SKBitmap.Decode(codec, info);
              return bitmap ?? throw new InvalidOperationException("Failed to decode the bitmap.");
          }
      }
      
      public static SKBitmap? AutoOrient(SKBitmap bitmap, SKEncodedOrigin origin)
      {
          switch (origin)
          {
              case SKEncodedOrigin.BottomRight:
                  var rotated180 = new SKBitmap(bitmap.Width, bitmap.Height);
                  using (var surface = new SKCanvas(rotated180))
                  {
                      surface.RotateDegrees(180, bitmap.Width / 2, bitmap.Height / 2);
                      surface.DrawBitmap(bitmap, 0, 0);
                  }
                  return rotated180;
              case SKEncodedOrigin.RightTop:
                  var rotated90 = new SKBitmap(bitmap.Height, bitmap.Width);
                  using (var surface = new SKCanvas(rotated90))
                  {
                      surface.Translate(rotated90.Width, 0);
                      surface.RotateDegrees(90);
                      surface.DrawBitmap(bitmap, 0, 0);
                  }
                  return rotated90;
              case SKEncodedOrigin.LeftBottom:
                  var rotated270 = new SKBitmap(bitmap.Height, bitmap.Width);
                  using (var surface = new SKCanvas(rotated270))
                  {
                      surface.Translate(0, rotated270.Height);
                      surface.RotateDegrees(270);
                      surface.DrawBitmap(bitmap, 0, 0);
                  }
                  return rotated270;
              default:
                  return bitmap;
          }
      }
      ```

2. **Handle Image Metadata Before Loading**  
   Use the helper methods to load and correct the image orientation.

      ```csharp
      private void LoadImage_Clicked(object sender, EventArgs e)
      {
          using var imageStream = File.OpenRead("MyImage.png");
          var bitmap = LoadBitmapWithOrigin(imageStream, out var origin);
          var rotatedBitmap = AutoOrient(bitmap, origin);
      
          SKImage image = SKImage.FromPixels(rotatedBitmap.PeekPixels());
          imageEditor.Source = ImageSource.FromStream(() => image.Encode().AsStream());
      }
      ```

Replace `"MyImage.png"` with the appropriate file path. Use the corrected bitmap when loading the image into the ImageEditor.

## See Also

- [ImageEditor Documentation](https://docs.telerik.com/devtools/maui/controls/imageeditor/overview)
- [ImageEditor iOS EXIF Issue Discussion](https://feedback.telerik.com/maui/1600114-imageeditor-some-images-are-rotated-initially-when-displaying-in-the-editor)
- [SkiaSharp API Reference](https://docs.microsoft.com/en-us/dotnet/api/skiasharp)
