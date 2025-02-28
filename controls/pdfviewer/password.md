---
title: Password Protected Documents
page_title: .NET MAUI PDF Viewer Documentation - Password protected documents
description: Review how to configure the PDF Viewer for .NET MAUI.
position: 5
slug: pdfviewer-password
---

# Password-Protected PDF Document

To allow the users to open password-protected documents in the <a href="https://www.telerik.com/maui-ui/pdf-viewer" target="_blank">.NET MAUI PDF Viewer</a>, you must handle the `SourcePasswordNeeded` event.

* `SourcePasswordNeeded`&mdash;Occurs when a user password is needed to load the document in the PDF Viewer. The `SourcePasswordNeeded` event handler receives two parameters:
	* The sender argument, which is of type `object`, but can be cast to the `RadPdfViewer` type.
	* A `PasswordNeededEventArgs` object, which provides the `Password` property used to supply the user password.

The following example demonstrates how to use the `SourcePasswordNeeded` event:

```XAML
<telerik:RadPdfViewer x:Name="pdfViewer" 
                      SourcePasswordNeeded="pdfViewer_SourcePasswordNeeded" />
```

The next code snippet represents the event handler:

```C#
private void pdfViewer_SourcePasswordNeeded(object sender, Telerik.Windows.Documents.Fixed.FormatProviders.Pdf.Import.PasswordNeededEventArgs e)
{
    e.Password = "my_user_password_here";
}
```

## See Also

- [All Available Commands]({%slug pdfviewer-commands%})
- [Review PDF Viewer Toolbar]({%slug pdfviewer-toolbar%})
