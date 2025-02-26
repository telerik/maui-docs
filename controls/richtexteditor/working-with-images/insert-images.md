---
title: Insert and Edit Images
page_title: .NET MAUI RichTextEditor Documentation - Insert and Edit Images
description: Learn more about the toolbar items and how they work with images in the Telerik UI for .NET MAUI RichTextEditor control.
position: 2
slug: richtexteditor-insert-images
---

# Toolbar Items for Working With Images

This article describes the built-in toolbar items for insert and edit images in the [.NET MAUI RichTextEditor]({%slug richtexteditor-overview%}) control.

## Insert Images

Use the following toolbar items for adding/inserting an image in the editor. 

* `RichTextEditorAddImageToolbarItem`&mdash;Allows you to add an image; the RichTextEditor `PickImage` event is fired, so you can handle the logic for selecting an image. The toolbar is enabled if no image is selected.
* `RichTextEditorAddOrEditImageToolbarItem`&mdash;Adds or edits images depending whether image is selected. If image is selected, the editor opens a dialog to edit the image. If image is not selected the `PickImage` event fires.
* `RichTextEditorImageNavigationToolbarItem`&mdash;Adds images or navigates to additional toolbar items depending whether image is selected. If image is selected, the editor navigates to image operation toolbar items. If image is not selected the `PickImage` event fires.

## Additional Toolbar Items for Image Operations

The `RichTextEditorImageNavigationToolbarItem` has the following items: 

* `RichTextEditorEditImageToolbarItem`&mdash;Allows you to resize the image. In addition the toolbar allows you to pick an image (the RichTextEditor.`PickImage` event is fired) if you haven't selected one. Check [Edit Image Toolbar Item]({%slug richtexteditor-insert-images%}#edit-image-toolbaritem) for more details.
* `RichTextEditorCutToolbarItem`&mdash;Allows you to cut the selected HTML/image to the clipboard.
* `RichTextEditorCopyToolbarItem`&mdash;Allows you to copy the selected HTML/image to the clipboard. 
* `RichTextEditorPasteHtmlToolbarItem`&mdash;Allows you to paste HTML/image from the clipboard.
* `RichTextEditorRemoveImageToolbarItem`&mdash;Allows you to remove the currently selected image from the document.

How the editing toolbar looks when image is selected: 

![.NET MAUI RichTextEditor Add Image](../images/rte-image-operation-toolbar-items.png)

## Edit Image Toolbar Item

`RichTextEditorEditImageToolbarItem` allows you to resize the image and pick an image. When tapping on the `RichTextEditorImageDialogToolbarItem`, a dialog is displayed. The options for customization are described in the table below:

| RichTextEditor ImageDialog ToolbarItem Options | Description |
| ------------- | --------------- |
| `Text` |  |
| `RichTextEditorFontSizeToolbarItem` |  |
| `ResizeLabelText` | Defines the text of the `Resize` Label. Default value `Resize:` |
| `MinimumLabelText` | Defines the text of the Minimum. Default value `0%` |
| `MaximumLabelText` | Defines the text of the Maximum. Default value `100%` |
| `PickButtonText` | Defines the text of the button(`RadButton`) that allows you to pick images. Note that `PickImage` event is raised when `PickButton` is pressed. |
| `HeaderText` | Defines the header text value. Default string `Image` |
| `PopupContentStyle` | Defines the Style applied to the popup content. |
| `PopupContentTemplate` | Defines  the control template of the popup. |
| `PopupOutsideBackgroundColor` | Defines the backgrounf color applied outside of the popup content. |
| `OkButtonText` | Defines the text for Ok button. Default value `Ok` |
| `CancelButtonText` | Defines the text for Cancel button. Default value: `Cancel` |

![.NET MAUI RichTextEditor Add Image](../images/rte-edit-image-dialog.png)

## ImagePickerToolbar Item

* `RichTextEditorImagePickerToolbarItem`(`Telerik.Maui.Controls.RichTextEditor.RichTextEditorListPickerButtonToolbarItem`)&mdash;Allows you to pick an image from a collection of pre-defined images.

![.NET MAUI RichTextEditor ImagePicker Toolbar](../images/rte-custom-image-picker.png)

### Example

**1.** RichTextEditor and toolbar definitions in XAML:

<snippet id='richtexteditor-custom-image-picker' />

In addition to this, you need to add the following namespace:

**2.** Add the `telerik` namespaces:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** The `VieWModel` for the `ImagePicker` Items Source and RichTextEditor Source:

<snippet id='richtexteditor-customimage-viewmodel' />

>important For the RichTextEditor Custom Image Picker example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) RichTextEditor -> Features category.

## See Also

- [Commands]({%slug richtexteditor-commands%})
- [Configure the RichTextEditor]({%slug richtexteditor-configuration%})
- [Events]({%slug richtexteditor-events%})
- [Working with images]({%slug richtexteditor-images-overview%})
- [Hyperlinks]({%slug richtexteditor-hyperlink-support%})