---
title: Displaying Thumbnails of Multiple PDFs in a Single View with .NET MAUI
description: Learn how to generate and display thumbnails for the first page of multiple PDF files in a single list box view, and open the selected PDF in a PDFViewer for .NET MAUI.
type: how-to
page_title: How to Display and Select PDF Thumbnails in a .NET MAUI Application
slug: display-select-pdf-thumbnails-dotnet-maui
tags: pdfviewer, .net maui, pdf, thumbnails, list box, pdf processing
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.0.0 | Telerik UI for .NET MAUI PDF Viewer | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 


## Description

I need a way to display the first page of multiple PDF files as thumbnails. Then display the thumbnails in a list. When a thumbnail is clicked, the respective full PDF document should open in a separate PDF Viewer.

This knowledge base article also answers the following questions:
- How can I display thumbnails of PDF files in a list using .NET MAUI?
- How do I open a PDF in a PDFViewer when its thumbnail is clicked in .NET MAUI?
- How to generate and use thumbnails of PDF pages in a .NET MAUI application?

## Solution

To achieve this, follow the steps in the [Generating and Displaying PDF Thumbnails](#generating-and-displaying-pdf-thumbnails) and [Loading PDF Documents in a PDF Viewer](#loading-pdf-documents-in-a-pdf-viewer) sections.

### Generating and Displaying PDF Thumbnails

1. Use the Telerik PDF Processing library ([RadPdfProcessing](https://docs.telerik.com/devtools/document-processing/libraries/radpdfprocessing/overview)) to convert the first page of each PDF file into an image thumbnail. Refer to this blog post for guidance: [Turn PDF Pages Into Images With PdfProcessing](https://www.telerik.com/blogs/turn-pdf-pages-images-pdfprocessing).

2. Iterate through each PDF file, extract the first page, and save it as an image. Manage the storage of these images appropriately on the device.

3. Create a collection that contains the image paths and the PDF file names. Bind this collection to a list control in your .NET MAUI application. Use an `<Image/>` element to display each thumbnail and a `<Label>` to show the document name.

Define the `RadCollectionView` in XAML:

```xml
<telerik:RadCollectionView ItemsSource="{Binding ListOfDocuments}" 
                           ItemTapped="RadCollectionView_ItemTapped">
    <telerik:RadCollectionView.ItemTemplate>
        <DataTemplate>
            <VerticalStackLayout>
                <Image Source="{Binding YourImage}" />
                <Label Text="{Binding YourPdfDocumentName}" />
            </VerticalStackLayout>
        </DataTemplate>
    </telerik:RadCollectionView.ItemTemplate>
</telerik:RadCollectionView>
```

Implement the `ItemTapped` event to handle thumbnail selection and navigate to a new page where the PDF Viewer is defined. Pass the selected PDF document to the `PdfViewer.Source` property.

### Loading PDF Documents in a PDF Viewer

Use the [PDF Viewer for .NET MAUI](https://docs.telerik.com/devtools/maui/controls/pdfviewer/display-documents) to display the selected PDF document. The PDF Viewer has a `Source` property, which you should set to the selected PDF document during navigation.

```csharp
// In the navigation logic from the list box to the PDFViewer page
pdfViewer.Source = selectedPdfDocumentPath;
```

## See Also

- [RadPdfProcessing Overview](https://docs.telerik.com/devtools/document-processing/libraries/radpdfprocessing/overview)
- [Displaying Documents in PDF Viewer for .NET MAUI](https://docs.telerik.com/devtools/maui/controls/pdfviewer/display-documents)
- [Turn PDF Pages Into Images With PdfProcessing Blog Post](https://www.telerik.com/blogs/turn-pdf-pages-images-pdfprocessing)
