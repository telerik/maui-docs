---
title: Overview
page_title: Xamarin RichTextEditor Documentation | Working with Images
description: Check our &quot;Working with Images&quot; documentation article for Telerik RichTextEditor for Xamarin control.
tags: edit, add, delete, images, insert images
position: 1
slug: richtexteditor-images-overview
---

# Overview

RichTextEditor control allows you to add(insert), cut, copy, paste, resize and delete images using built-in toolbar items. 

![RichTextEditor AddImage](../images/add-image-toolbar-item.png) 
![RichTextEditor AddImage](../images/rte-edit-image-toolbar-items.png)

You can add images in the RichTextEditor by using the predefined toolbar items:

* `RichTextEditorAddImageToolbarItem`&mdash;Allows you to add an image - the RichTextEditor `PickImage` event is fired, so you can handle the logic for selecting an image. The toolbar is enabled if no image is selected.
* `RichTextEditorAddOrEditImageToolbarItem`&mdash;This toolbar item adds or edits images depending whether image is selected. If image is selected, the editor opens a dialog to edit the image. If image is not selected the `PickImage` event fires.
* `RichTextEditorImageNavigationToolbarItem`&mdash;This toolbar item adds or edits images depending whether image is selected. If image is selected, the editor navigates to image operation toolbar items. If image is not selected the `PickImage` event fires.

You can insert images from Uri, Data(byte []), Stream, File. The image source is of type `RichTextImageSource`. 

* `RichTextImageSource FromData(byte[] data, RichTextImageType type)`
* `RichTextImageSource FromFile(string path)`
* `RichTextImageSource FromFile(string path, RichTextImageType type)`
* `RichTextImageSource FromStream(Stream stream, RichTextImageType type)`
* `RichTextImageSource FromStream(Func<Stream> stream, RichTextImageType type)`
* `RichTextImageSource FromStream(Func<Task<Stream>> stream, RichTextImageType type)`
* `RichTextImageSource FromStream(Func<CancellationToken, Task<Stream>> stream, RichTextImageType type)`
* `RichTextImageSource FromUrl(string uri)`


Also you have to point out the image format type. The supported image format types(of type `RichTextImageType`) are:

* **Gif**
* **Jpeg**
* **Png**
* **Svg**
* **Webp**

## Permissions if adding images from gallery

>important If you want to work with images from the device gallery, then you have to grant permissions.

Add images using the predefined toolbar items - `RichTextEditorAddOrEditImageToolbarItem` on Desktop and `RichTextEditorImageNavigationToolbarItem` on Mobile. Both toolbar items provide a way to pick an image directly. The RichTextEditor `PickImage` event is fired. You need to manually implement the logic for selecting an image inside the `PickImage` event handler. 

```C#
private void OnPickImage(object sender, Telerik.Maui.Controls.RichTextEditor.PickImageEventArgs e)
{
// add your custom logic here
}
```

## Events 

* `PickImage`&mdash;Raised when the user has requested to pick an image in the RadRichTextEditor. The PickImage event handler receives two parameters:
	* The `sender` which is the RichTextEditor control;
	* `PickImageEventArgs` provides the following methods:
		* `Accept`&mdash;Invoke this method when the user has picked an image. Recieves one paramerter `imagesource` of type `RichTextImageSource`(Specifies the `RichTextImageSource` for the picked image);
		* `Cancel`&mdash;Invoke this method when the user has cancelled the operation;

* `InsertImageError`&mdash;Raised when trying to insert an image in the RadRichTextEditor. The InsertImageError event handler receives two parameters:
	* The `sender` which is the RichTextEditor control;
	* `InsertImageErrorEventArgs` provides the following methods:
		* `Source`&mdash;of type `RichTextImageSource`. The property allows you to get the source of the image (read-only property).
		* `Error`&mdash;of type `Exception`. Specifies the exception that is raised when image cannot be inserted.

* `IsImageSelectedChanged`&mdash;Raised when an image inside the editor is selected. The IsImageSelectedChanged event handler receives two parameters:
	* The `sender` which is the RichTextEditor control;
	* `RadValueChangedEventArgs<bool>` provides `NewValue` and `PreviousValue` properties of type `TValue`.

## Methods

* `GetImageAsync` method returns asynchronously an object of type RichTextImage which represents the current selected image (or null in case there is no image). The RichTextImage object contains the Source, Title, Width and Height of the image;

## Commands

* `InsertImageCommand`(`ICommand`)&mdash;Uses for inserting images in the editor. The command takes a single parameter of type `RichTextImage`. The `RichTextImage` object contains the source, title, width, height of the image. If you do not set width and height explicitly, the image will be added with its original size. 
* `RemoveImageCommand`(`ICommand`)&mdash;uses for removing images from the editor.

## See Also

