---
title: Link Annotations
page_title: .NET MAUI PdfViewer Documentation - Link Annotations
description: Review the link annotations features introduced in Telerik .NET MAUI PdfViewer control.
position: 6
slug: pdfviewer-annotations
---

# Link Annotations

The Telerik .NET MAUI PdfViewer supports Link annotations. If you open a PDF file that includes hyperlinks to absolute URIs, you can tap any of them and have a browser open, navigated to the respective address. In addition, if there are links pointing to bookmarks in the same document, the view port scrolls to the destination specified in the link.

![.NET MAUI PdfViewer Link Annotation](images/pdfviewer-link-annotations.png)

PdfViewer provides the following `LinkAnnotationTapped` event which allows implementing custom logic related to links in the pdf document:

* `LinkAnnotationTapped`&mdash;Occurs when you click on an annotation such as a hyperlink. It comes handy when you want to detect or even cancel the opening of a web page. The `LinkAnnotationTapped` event handler receives two parameters:
	* The `sender` argument which is of type *object*, but can be cast to the `RadPdfViewer` type.
	* A `LinkAnnotationTappedEventArgs` object which provides the link the user tapped on via the `LinkAnnotation` property and a cancellation option via the `Handled` boolean property. The `LinkAnnotation` has information of its Action, i.e if it is a `UriAction` or `GoToAction` (link to a position in the sampe document).

## Example

The example below demonstrates how you could detect whether the link annotation leads to a URI or a concrete position in the document, and cancel the navigation in the first case. 

Then, you could implement additional logic for requesting a confirmation from the end user whether to navigate outside of the app in the case of a hyperlink.

**1.** Add the PdfViewer definition with the event:

<snippet id='pdfviewer-features-annotations-xaml' />

**2.** And the `LinkAnnotationTapped` event handler:

<snippet id='pdfviewer-annotations-event' />

The result on different platforms after tapping on a hyperlink:

![.NET MAUI PdfViewer Link Annotation Event](images/pdfviewer-link-annotationsevent.png)

> For the PrfViewer Annotations example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to PdfViewer -> Features category.

## See Also

- [PdfViewer Toolbar]({%slug pdfviewer-toolbar%})
