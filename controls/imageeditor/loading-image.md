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

`RadImageEditor` definition:

<snippet id='imageeditor-busy-template'/>

Add the namespace used:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

 >important For the ImageEditor Busy Template example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## Events

The ImageEditor control provides an event that is raised when an image is loaded in the editor&mdash;`ImageLoaded`.
    * The sender argument which is of type object, but can be cast to the `RadImageEditor` type.
	* An `System.EventArgs` object.

**Example with ImageLoaded**

```XAML
 <telerik:RadImageEditor x:Name="imageEditor" ImageLoaded="imageEditor_ImageLoaded"/>
```

And the event implementation:

```C#
private void imageEditor_ImageLoaded(object sender, EventArgs e)
{
   // implement your logic here: 
}
```

## See Also

- [Zooming Image]({%slug imageeditor-zooming-image%})
- [Saving Image]({%slug imageeditor-saving-image%})