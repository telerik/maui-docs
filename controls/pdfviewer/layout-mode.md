---
title: Layout Modes
page_title: .NET MAUI PdfViewer Documentation - Layout Modes
description: Review the different layout modes of the Pdfviewer for .NET MAUI.
position: 2
slug: pdfviewer-layout-modes
---

## Layout Modes

You could easily set one of the two layout modes that the control provides through its `LayoutMode` property.

The available options are:

* `ContinuousScroll`&mdash;Displays pages in a continuous vertical column.
* `SinglePage`&mdash;Displays one page at a time.

>note By default the PdfViewer LayoutMode property is set to `ContinuousScroll`.

>tip The RadPdfViewer LayoutMode could be triggered through the `ToggleLayoutModeCommand` and the `ToggleLayoutModeToolbarItem`.

Here is how the PdfViewer looks when `LayoutMode` is set to `ContinuousScroll`:

![PdfViewer ContinuousScroll](images/pdfviewer-continuous-scroll.png "PdfViewer ContinuousScroll")

And when the `LayoutMode` property is set to `SinglePage`:

![PdfViewer SinglePage](images/pdfviewer-single-page.png "PdfViewer SinglePage")

## See Also

- [Commands]({%slug pdfviewer-commands%})
- [PdfViewer Toolbar]({%slug pdfviewer-toolbar%})
