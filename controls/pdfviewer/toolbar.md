---
title: PdfViewer Toolbar
page_title: .NET MAUI PdfViewer Documentation - PdfViewer Toolbar
description: Review all predefined items in the .NET MAUI PdfViewer control.
position: 3
slug: pdfviewer-toolbar
---

# PdfViewer Toolbar

PdfToolbar includes some of commands that the PdfViewer provides. You have also the option to include additional toolbar items to the PdfViewerToolbar with a custom command.  

## Predefined Toolbar Items

PdfToolbar provides the following toolbar items:

* `PdfViewerZoomInToolbarItem`
* `PdfViewerZoomOutToolbarItem`
* `PdfViewerNavigateToNextPageToolbarItem`
* `PdfViewerNavigateToPreviousPageToolbarItem`
* `PdfViewerFitToWidthToolbarItem`

>note PdfToolbarItems inherit from `ButtonToolbarItem`. All properties applicable for `ButtonToolbarItem` are available for the PdfViewer toolbar items. 

### Example

**1.** Use the following snippet to define the RadPdfViewer and RadPdfToolbar:

<snippet id='pdfviewer-toolbar-xaml'/>

**2.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Then add the following code to visualize the pdf document:

<snippet id='pdfviewer-toolbar'/>

>The snippet above shows one of the approaches for loading a pdf document inside RadPdfViewer just for the purpose of the example. For more details on various ways for loading the document check [Key Features: Pdf Document Visualization]({%slug pdfviewer-key-features%}#pdf-document-visualization) topic.

This is the result:

![.NET MAUI PdfViewer Toolbar](images/pdfviewer-toolbar.png "PdfViewer Toolbar")

> For the PdfViewer Toolbar example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to PdfViewer -> Toolbar category.

## Custom Toolbar Item

You can easily add custom toolbar items to the PdfToolbar bound with a custom command. This is implemented by using the `ButtonToolbarItem`.

Here is an example showing how to add a custom ToolbarItem with a sample command bound to it. The command is used just to display a message with the PdfDocument file size.

**1.** Add the PdfViewer and the PdfToolbar controls to your page:

<snippet id='pdfviewer-toolbar-customcommand-xaml' />

**2.** Load a sample pdf document in code-behind:

<snippet id='pdfviewer-toolbar-customcommand' />

**3.** ViewModel class. In the ViewModel get a reference to the `RadFixedDocument` instance through the `Document` property of the PdfViewer as well as execute the `DisplayFileSizeCommand` bound to the `Command` property of the custom ToolbarItem:

<snippet id='pdfviewer-toolbar-customcommand-vm' />

Check below the result on different platforms:

![PdfToolbar Custom ToolbarItem](images/pdfviewer-toolbar-customitem.png)

> For the PdfViewer Custom Toolbar example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to PdfViewer -> Toolbar category.

## See Also

- [Commands]({%slug pdfviewer-commands%})
