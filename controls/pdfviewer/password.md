---
title: Password Protected Documents
page_title: .NET MAUI PDF Viewer Documentation - Password protected documents
description: Review how to configure the PDF Viewer for .NET MAUI.
position: 5
slug: pdfviewer-password
---

# Password-protected PDF Document

* `SourcePasswordNeeded`&mdash;Occurs when a user password is needed to load the document in PDF Viewer. The SourcePasswordNeeded event handler receives two parameters:
	* The sender argument which is of type `object`, but can be cast to the `RadPdfViewer` type.
	* A `PasswordNeededEventArgs` object which provides `Password` property used to supply the user password.

An example of `SourcePasswordNeeded` event usage:

```XAML
<telerik:RadPdfViewer x:Name="pdfViewer" 
                      SourcePasswordNeeded="pdfViewer_SourcePasswordNeeded" />
```

Add the event handler:

```C#
private void pdfViewer_SourcePasswordNeeded(object sender, Telerik.Windows.Documents.Fixed.FormatProviders.Pdf.Import.PasswordNeededEventArgs e)
{
    e.Password = "my_user_password_here";
}
```

## See Also

- [Commands]({%slug pdfviewer-commands%})
- [PDF Viewer Toolbar]({%slug pdfviewer-toolbar%})
