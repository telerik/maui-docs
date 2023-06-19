---
title: Display Documents
page_title: .NET MAUI PDF Viewer Documentation - Display Documents
description: Review the options for visualizing PDF documents in the PDF Viewer for .NET MAUI.
position: 2
slug: pdfviewer-display-documents
---

## PDF Document Visualization

The Telerik UI for .NET MAUI PDF Viewer control enables you to visualize PDF documents through the `Source` property of type `Telerik.Maui.Controls.PdfViewer.DocumentSource`. 

## Visualize Documents from a Fixed Document

The PDF Viewer allows you to load the PDF document from a stream by using the `RadFixedDocument` element.

By using this approach, you have more control over the loading process, for example, you can modify the document after importing it and before assigning it as a `Source` to the PDF Viewer control. For more details, check [`RadFixedDocument`](https://docs.telerik.com/devtools/document-processing/libraries/radpdfprocessing/model/radfixeddocument) topic from `RadPdfProcessing` documentation. 

The following example demonstrates how to visualize a document by using the `RadFixedDocument` method.

<snippet id='pdfviewer-key-features-source-fixed-method' />

>note The example shows a PDF document visualized as an embedded resource. This is one of the options for loading a PDF with the PDF Viewer control. 

## Visualize Documents from URI

The following example demonstrates how to visualize a document from a URI:

<snippet id='pdfviewer-key-features-source-uri' />

Alternatively, you can also the `UriDocumentSource` class. In this example, the `GetUri()` method returns a valid and accessible URL:

```C#
Uri uri = this.GetUri();
this.pdfViewer.Source = new UriDocumentSource(uri);
```

## Visualize Documents from File

You can visualize the PDF document from a file located on a device by passing the file path to the `Source` property of the PDF Viewer control:

```C#
this.pdfViewer.Source = filePath;
```

In the example above, the `filePath` variable is a string that contains the path to the file location.

To validate that the file exists on the device, you can use the following code:

```C#
System.IO.File.OpenRead(filePath);
```

> Your app must have all required permissions to use the file resources. Failing to grant these permissions will result in an error.

## Visualize Documents from Byte Array

The following example demonstrates how to visualize documents from a byte array.

<snippet id='pdfviewer-key-features-source-byte' />

Alternatively, you can use the `ByteArrayDocumentSource` class:

```C#
byte[] bytes = this.GetBytes();
this.pdfViewer.Source = new ByteArrayDocumentSource(bytes, true);          
```

## Visualize Documents from a Stream

The following example demonstrates how to visualize documents from a stream:

<snippet id='pdfviewer-key-features-stream' />

Alternatively, you can use the `StreamDocumentSource` class:

```C#
Assembly assembly = typeof(KeyFeatures).Assembly;
string fileName = assembly.GetManifestResourceNames().FirstOrDefault(n => n.Contains("pdfviewer-overview.pdf"));
Stream stream = assembly.GetManifestResourceStream(fileName);
var streamDocumentSource = new StreamDocumentSource();
streamDocumentSource.Import(stream);
this.pdfViewer.Source = streamDocumentSource;
```

> When using `StreamDocumentSource`, the stream must stay open while the PDF Viewer is in use because the PDF import operates through [read on demand](#read-on-demand-loading). As a result, you must manually close the stream when the PDF Viewer is no longer used.

### Read-On-Demand Loading

The PDF Viewer control implements read-on-demand loading, and each page of the document loads dynamically only when it is shown in the PDF Viewer. When that page isn't in the view area, it gets unloaded. The stream that holds the document stays opened while the document is used in PDF Viewer.

## Get Document Reference

By using the `Document` property of `RadPdfViewer`, you can get a reference to the `RadFixedDocument` imported by the document's source. For more details, check [`RadFixedDocument`](https://docs.telerik.com/devtools/document-processing/libraries/radpdfprocessing/model/radfixeddocument) topic in the documentation of the RadPdfProcessing library. 

## See Also

- [Commands for PDF Viewer]({%slug pdfviewer-commands%})
- [PDF Viewer Toolbar]({%slug pdfviewer-toolbar%})
