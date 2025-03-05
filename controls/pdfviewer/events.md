---
title: Events
page_title: .NET MAUI PDF Viewer Documentation - Events
description: Review all events the Telerik PDF Viewer for .NET MAUI control provides.
position: 9
slug: pdfviewer-events
---

# Events

The Telerik UI for .NET MAUI PDF Viewer provides various events that allow you to control the behavior of the component.

## Page Elements Loaded

The <a href="https://www.telerik.com/maui-ui/pdf-viewer" target="_blank">.NET MAUI PDF Viewer</a> raises the `PageElementsLoaded` event when all elements on the page are loaded. Use this event to alter the page content before it is rendered. This event is raised on a background thread.

The `PageElementsLoaded` event handler receives two parameters:
* `sender`&mdash;The PDF Viewer control.
* `PageElementsLoadedEventArgs`&mdash;The Object which has a reference to the `Page`(`RadFixedPage`).

The following example demonstrates how to use the `PageElementsLoaded` event:

<snippet id='pdfviewer-page-elements-loaded' />

The next example shows how to add the event handler:

<snippet id='pdfviewer-page-element-loaded-event' />

## Handling Exceptions in the Source

In some cases, the PDF Viewer will fail to load the passed PDF document. The reason can be an invalid stream/inaccessible URL or invalid data in the document itself. To handle these corner cases, use the `SourceException` event of the PDF Viewer. In addition, you can show a user-friendly message to the users through `SourceExceptionTemplate`.

The example below shows how to use the `RadPdfViewer` API for handling source exceptions.

**1,.** Define the `RadPdfViewer` control and apply a `SourceExceptionTemplate`. The snippet below demonstrates a sample template with only one Label which holds the message. 

<snippet id='pdfviewer-source-exception-xaml' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** And the `SourceException` event handler:

<snippet id='pdfviewer-sourceexception-eventhandler' />

> For a runnable PDF Viewer example with the Source Exception event, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **PdfViewer > Features**.

## See Also

- [PdfViewer Toolbar]({%slug pdfviewer-toolbar%})
