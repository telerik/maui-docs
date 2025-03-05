---
title: Styling
page_title: .NET MAUI PDF Viewer Documentation - Toolbar Styling
description: Learn how to style the Telerik PDF Viewer Toolbar items.
position: 7
slug: pdfviewer-toolbar-styling
---

# .NET MAUI PDF Viewer Toolbar Styling

The <a href="https://www.telerik.com/maui-ui/pdf-viewer" target="_blank">.NET MAUI PDF Viewer</a> provides a flexible styling API for its toolbar items. 

As the `PDFViewerToolbar` is based on the `RadToolbar` control, all toolbar items in the PDF Viewer inherit from `ButtonToolbarItem`. All styling properties available for the `ButtonToolbarItem` are also applicable for the PDF toolbar items. 

Here is an example:

**1.** PDF Viewer and Toolbar definitions in XAML:

<snippet id='pdfviewer-toolbar-styling-xaml'/>

**2.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.**: Define the style in the page's resources:

<snippet id='pdfviewer-toolbar-styling-resources'/>

**4.** Pass the document to the `PdfViewer.Source`:

<snippet id='pdfviewer-toolbar'/>

Here is the result on the image below:

![.NET MAUI PdfViewer ToolbarStyling](images/pdf-toolbar-styling.png)

## See Also

- [RadPdfProcessing library](https://docs.telerik.com/devtools/document-processing/libraries/radpdfprocessing/overview)
