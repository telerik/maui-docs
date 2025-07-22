---
title: Share PDF Files in Your Mobile and Desktop Apps.
description: Learn how to share pdf files using the PDF Viewer Toolbar in your .NET MAUI application.
type: how-to
page_title: How to Share PDF Files in Your .NET MAUI Application
slug: share-pdf-files-mobile-desktop
tags: maui, pdf, share files, share documents, telerik, dotnet, pdf viewer
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.0 | Telerik UI for .NET MAUI PDF Viewer | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

Learn how to share PDF files in your .NET MAUI application.

This knowledge base article also answers the following questions:
- How can I transfer PDF files in .NET MAUI application?
- How can I use the PDF Viewer Toolbar for Sharing PDF documents?

## Solution

For sharing files, use the [.NET MAUI Share File API](https://learn.microsoft.com/en-us/dotnet/maui/platform-integration/data/share?view=net-maui-9.0&tabs=android). The `Share` command will be executed from a custom toolbar `ButtonToolbarItem` inside the [PDF Viewer Toolbar]({%slug pdfviewer-toolbar%}).

**1.** Define the [PDF VIewer]({%slug pdfviewer-overview%}) and [PDF Viewer Toolbar]({%slug pdfviewer-toolbar%}):

```XAML
<Grid>
	<Grid.RowDefinitions>
		<RowDefinition Height="Auto"/>
		<RowDefinition />
	</Grid.RowDefinitions>
	<telerik:RadPdfViewerToolbar PdfViewer="{Binding Source={x:Reference pdfViewer}}">

		<telerik:ButtonToolbarItem Text="Share" 
                                   Command="{Binding ShareDocumentCommand}" />
	</telerik:RadPdfViewerToolbar>
	<telerik:RadPdfViewer x:Name="pdfViewer" 
						  Grid.Row="1"
                          Document="{Binding Document, Mode=OneWayToSource}" />
</Grid>
```

**2.** In this example, load the document as `Embedded Resource`.

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
		this.ShareDocumentCommand = new Command(this.ShareDocument);
	}

	private async void ShareDocument(object obj)
	{
		await ShareAsync();
	}

	// share pdf document
	private async Task ShareAsync()
	{
		Assembly assembly = typeof(MainPage).Assembly;
		string fileName = assembly.GetManifestResourceNames().FirstOrDefault(n => n.Contains("pdf-overview.pdf"));
		Stream stream = assembly.GetManifestResourceStream(fileName);
		var cacheFile = Path.Combine(FileSystem.CacheDirectory, "pdf-overview.pdf");
		using (var file = new FileStream(cacheFile, FileMode.Create, FileAccess.Write))
		{
			stream.CopyTo(file);
		}
		var request = new ShareFileRequest
		{
			Title = "Share pdf document",
			File = new ShareFile(cacheFile)
		};
		await Share.Default.RequestAsync(request);
	}

	public RadFixedDocument Document { get; set; }

	public ICommand ShareDocumentCommand { get; set; }
}
```

## See Also

- [PDF Viewer Toolbar]({%slug pdfviewer-toolbar%})
- [Share Files in .NET MAUI](https://learn.microsoft.com/en-us/dotnet/maui/platform-integration/data/share?view=net-maui-9.0&tabs=android)