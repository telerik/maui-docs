---
title: Layout Modes
page_title: .NET MAUI PDF Viewer Documentation - Layout Modes
description: Review the different layout modes of the PDF viewer for .NET MAUI.
position: 4
slug: pdfviewer-layout-modes
---

## Layout Modes

The Telerik UI for .NET MAUI PDF Viewer supports two layout modes that you can set through its `LayoutMode` property.

The available options are:

* `ContinuousScroll` (default)&mdash;Displays pages in a continuous vertical column.
* `SinglePage`&mdash;Displays one page at a time.

The current `LayoutMode` can be changed through the `ToggleLayoutModeCommand` and the `ToggleLayoutModeToolbarItem` [`RadPdfViewer` commands]({%slug pdfviewer-commands%}).

Here is how the PDF Viewer looks when the `LayoutMode` is set to `ContinuousScroll`:

![.NET MAUI PDF Viewer ContinuousScroll](images/pdf-continousscroll.png "PdfViewer ContinuousScroll")

The next image shows the PDF Viewer when the `LayoutMode` property is set to `SinglePage`:

![.NET MAUI PDF Viewer SinglePage](images/pdf-singlepage.png "PdfViewer SinglePage")

## See Also

- [All Commands PDF Viewer provides]({%slug pdfviewer-commands%})
- [PdfViewer Toolbar]({%slug pdfviewer-toolbar%})
