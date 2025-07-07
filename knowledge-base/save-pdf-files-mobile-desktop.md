---
title: Save PDF Files in Your Mobile and Desktop Apps.
description: Learn how to save pdf files using the PDF Viewer Toolbar in your .NET MAUI application.
type: how-to
page_title: How to Save PDF Files in Your .NET MAUI Application
slug: save-pdf-files-mobile-desktop
tags: maui, pdf, save files, save documents, telerik, dotnet, pdf viewer
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.0 | Telerik UI for .NET MAUI PDF Viewer | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 


## Description

Learn how to save pdf files in your .NET MAUI application.

This knowledge base article also answers the following questions:
- How can I save `PDF` files?
- How can I use the PDF Viewer Toolbar for Saving `PDF` documents?

## Solution

For saving files we will use the [.NET MAUI File System Helper API](https://learn.microsoft.com/en-us/dotnet/maui/platform-integration/storage/file-system-helpers?view=net-maui-9.0&tabs=android). The `Save` command will be executed from a custom toolbar `ButtonToolbarItem` inside the [PDF Viewer Toolbar]({%slug pdfviewer-toolbar%}).

**1.** Define the [PDF VIewer]({%slug pdfviewer-overview%}) and [PDF Viewer Toolbar]({%slug pdfviewer-toolbar%}):

```XAML
<Grid>
	<Grid.RowDefinitions>
		<RowDefinition Height="Auto"/>
		<RowDefinition />
	</Grid.RowDefinitions>
		<telerik:RadPdfViewerToolbar PdfViewer="{Binding Source={x:Reference pdfViewer}}">
			<telerik:ButtonToolbarItem Text="Share" Command="{Binding SaveDocumentCommand}" />
	</telerik:RadPdfViewerToolbar>
	<telerik:RadPdfViewer x:Name="pdfViewer" 
						  Grid.Row="1"
                          Document="{Binding Document, Mode=OneWayToSource}" />
</Grid>
```

**2.** for the demo the document is loaded as `Embedded Resource`.

```C#
Func<CancellationToken, Task<Stream>> streamFunc = ct => Task.Run(() =>
{
	Assembly assembly = typeof(MainPage).Assembly;
	string fileName = assembly.GetManifestResourceNames().FirstOrDefault(n => n.Contains("pdf-overview.pdf"));
	Stream stream = assembly.GetManifestResourceStream(fileName);
	return stream;
});
this.pdfViewer.Source = streamFunc;
```

**3.** Create a `ViewModel` and implement the `ShareDocumentCommand` which defines the Share API:

```C#
public class ViewModel
{
	public ViewModel()
	{
		this.SaveDocumentCommand = new Command(this.SaveDocument);
	}

	// save pdf document
	private void SaveDocument(object obj)
	{

		var fileName = "document.pdf";
		var localFolder = Environment.GetFolderPath(Environment.SpecialFolder.LocalApplicationData);
		var filePath = Path.Combine(localFolder, fileName);

		using (Stream output = File.OpenWrite(filePath))
		{
			new Telerik.Windows.Documents.Fixed.FormatProviders.Pdf.PdfFormatProvider().Export(this.Document, output);

			Application.Current.MainPage.DisplayAlert("Document is saved to local application data: ", filePath, "OK");
		}
	}

	public RadFixedDocument Document { get; set; }

	public ICommand SaveDocumentCommand { get; set; }
}
```

> Make sure the app is granted permissions to access local data.

## See Also

- [PDF Viewer Toolbar]({%slug pdfviewer-toolbar%})