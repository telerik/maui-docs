---
title: Displaying Semi-Transparent Watermarks in .NET MAUI PDF Viewer
description: Learn how to display semi-transparent watermarks in PDF documents using the PDF Viewer component from the UI for .NET MAUI suite.
type: how-to
page_title: How to Show Semi-Transparent Watermarks in MAUI PDFViewer
meta_title: Show Semi-Transparent Watermarks in .NET MAUI PDF Viewer
slug: display-semi-transparent-watermarks-maui-pdfviewer
tags: pdfviewer, .net maui, transparency, watermark, pageelementloaded
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | --- | ---- |
| 13.0.0 | Telerik UI for .NET MAUI PDF Viewer  | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

When displaying PDF documents in the [PDFViewer](https://www.telerik.com/maui-ui/documentation/controls/pdfviewer/overview) component for UI for .NET MAUI, watermarks with transparency may appear as solid colors. This happens because the component does not automatically render semi-transparent watermarks.

This knowledge base article also answers the following questions:
- How to enable transparency for watermarks in MAUI PDF Viewer?
- Why does the watermark appear solid in MAUI PDF Viewer?
- How to modify watermark transparency in .NET MAUI PDF Viewer?

## Solution

To display semi-transparent watermarks in the PDF Viewer, implement the following steps:

1. Subscribe to the `RadPdfViewer.PageElementsLoaded` event.
2. Enumerate the page's content elements.
3. Identify `TextFragment` objects that match the watermark text.
4. Set the fill color with transparency to the matching fragments.

Use the following XAML to define the PDFViewer and attach the `PageElementsLoaded` event.

```xml
<telerik:RadPdfViewer x:Name="pdfViewer"
                      PageElementsLoaded="pdfViewer_PageElementsLoaded"/>
```

Define the `PageElementsLoaded` event handler and implement the logic to apply transparency to the watermark text.

```csharp
private void pdfViewer_PageElementsLoaded(object sender, Telerik.Maui.Controls.PdfViewer.PageElementsLoadedEventArgs e)
{
    UpdateWatermarkTransparency(e.Page);
}

private static void UpdateWatermarkTransparency(RadFixedPage fixedPage)
{
    foreach (var contentElement in fixedPage.Content)
    {
        if (contentElement is Telerik.Windows.Documents.Fixed.Model.Text.TextFragment textBlock)
        {
            if (textBlock.Text.Contains("Watermark text!"))
            {
                // Set the fill color with transparency (e.g., 60% opacity red).
                textBlock.Fill = new RgbColor(60, 255, 0, 0);
            }
        }
    }
}
```

## See Also

- [PDF Viewer Overview](https://www.telerik.com/maui-ui/documentation/controls/pdfviewer/overview)
- [RadPdfViewer Events](hhttps://www.telerik.com/maui-ui/documentation/controls/pdfviewer/events)
- [TextFragment Documentation](https://www.telerik.com/document-processing-libraries/documentation/api/telerik.windows.documents.fixed.model.text.textfragment)
