---
title: Events
page_title: .NET MAUI PdfViewer Documentation - Events
description: Review all events the Telerik PdfViewer for .NET MAUI control provides.
position: 9
slug: pdfviewer-events
---

# Events

This article explains alll events the Telerik PdfViewer for .NET MAUI provides. 

## Event when elements in the page are loaded

PdfViewer privdes an event that is raised when all elements in the page are loaded&mdash;`PageElementsLoaded`. Use this event to alter the page content before it is rendered. This event is raised on a background thread.
The `PageElementsLoaded` event handler receives two parameters:
	* `sender`&mdash;the PdfViewer control.
	* `PageElementsLoadedEventArgs`&mdash;object which has a reference to the  `Page`(`RadFixedPage`).


## Handling exceptions in the source

In certain cases PdfViewer will not be able to load the passed Pdf document - it can be due to invalid stream/inaccessible URL or some invalid data in the document itself. PdfViewer provides a way to catch these cases through its `SourceException` event. In addition, you could show a user-friendly message to the users through `SourceExceptionTemplate`.

Check the example below which shows how to use the RadPdfViewer API for handling source exceptions.

**1,.** Define RadPdfViewer control and apply a `SourceExceptionTemplate`. The snippet below demonstrates a sample template with only one Label which holds the message. 

<snippet id='pdfviewer-source-exception-xaml' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** And the SourceException event handler:

<snippet id='pdfviewer-sourceexception-eventhandler' />

Check below how the defined SourceTemplateException looks:

![.NET MAUI PdfViewer SourceException](images/pdfviewer-sourceexceptiontemplate.png)

> For the PdfViewer SourceException example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to PdfViewer -> Features category.

## See Also

- [PdfViewer Toolbar]({%slug pdfviewer-toolbar%})
