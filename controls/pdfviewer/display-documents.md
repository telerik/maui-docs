---
title: Display Documents
page_title: .NET MAUI PdfViewer Documentation - Display Documents
description: Review the options for visualizing pdf documents in the PdfViewer for .NET MAUI.
position: 2
slug: pdfviewer-display-documents
---

## Pdf Document Visualization

.NET MAUI PdfViewer control enables you to visualize Pdf documents through the `Source` property of type *Telerik.XamarinForms.PdfViewer.DocumentSource*. 

## Visualize documents from FixedDocument

* `RadFixedDocument`&mdash;Used to load the pdf document from a stream.

>tip Using this approach you have more control over the loading process, for example, you could modify the document after it is imported and before it is assigned as a `Source` to the PdfViewer control. For more details check [RadFixedDocument](https://docs.telerik.com/devtools/document-processing/libraries/radpdfprocessing/model/radfixeddocument) topic from RadPdfProcessing documentation. 

**Example**

<snippet id='pdfviewer-key-features-source-fixed-method' />

>note The example shows a pdf document visualized as an EmbeddedResource. This is one of the options for loading a pdf with the PdfViewer control. 

## Visualize documents from Uri

<snippet id='pdfviewer-key-features-source-uri' />

or 
```C#
Uri uri = this.GetUri();
this.pdfViewer.Source = new UriDocumentSource(uri);
```

where `GetUri()` method returns a valid and accessible URL.

## Visualize documents from File

You can visualize the pdf document from a file located on a device (available since R1 2019 SP). You just need to pass the file path to the *Source* property of the PdfViewer control:

```C#
this.pdfViewer.Source = filePath;
```

where the filePath variable is a string that contains the path to the file location.

In order to make sure that the file exists on the device you could use the following code:

```C#
System.IO.File.OpenRead(filePath);
```

>important Please make sure that you have granted the app all the permissions needed before the resources are used. Otherwise, an error will be raised.

## Visualize documents from Byte Array

Here is a sample how to visualize documents from a byte array.

<snippet id='pdfviewer-key-features-source-byte' />

or
```C#
byte[] bytes = this.GetBytes();
this.pdfViewer.Source = new ByteArrayDocumentSource(bytes, true);          
```

## Visualize documents from a Stream

There are two ways: 

<snippet id='pdfviewer-key-features-stream' />

or

```C#
Assembly assembly = typeof(KeyFeatures).Assembly;
string fileName = assembly.GetManifestResourceNames().FirstOrDefault(n => n.Contains("pdfviewer-overview.pdf"));
Stream stream = assembly.GetManifestResourceStream(fileName);
var streamDocumentSource = new StreamDocumentSource();
streamDocumentSource.Import(stream);
this.pdfViewer.Source = streamDocumentSource;
```

>note If you choose the second approach with `StreamDocumentSource`, please keep in mind the stream must stay open while the PdfViewer is in use, because the pdf import is [ReadOnDemand](#readondemand-loading). This means that you'd need to manually close the stream when no longer using the PdfViewer.

## ReadOnDemand Loading

PdfViewer control provides ReadOnDemand loading of the pdf document, which means that each page of the document is loaded dynamically when necessary (when needed to be shown in the PdfViewer) and it is unloaded once it becomes invisible. The stream that holds the document stays opened while the document is used in PdfViewer.

## Document Reference

Through the `Document` property of RadPdfViewer you can get a reference to the **RadFixedDocument** imported by the DocumentSource. For more details check [RadFixedDocument](https://docs.telerik.com/devtools/document-processing/libraries/radpdfprocessing/model/radfixeddocument) topic from RadPdfProcessing documentation. 

## See Also

- [Commands]({%slug pdfviewer-commands%})
- [PdfViewer Toolbar]({%slug pdfviewer-toolbar%})
