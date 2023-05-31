---
title: Commands
page_title: .NET MAUI PdfViewer Documentation - Commands
description: Check our &quot;Commands&quot; documentation article for Telerik PdfViewer for Xamarin control.
position: 10
slug: pdfviewer-commands
---

# Commands

PdfViewer provides the following commands of type `ICommand`:

* `ZoomInCommand`
* `ZoomOutCommand`
* `NavigateToNextPageCommand`Navigates to next page.
* `NavigateToPreviousPageCommand`&mdash;Navigates to previous page.
* `NavigateToPageCommand`&mdash;Navigates to a concrete page.
* `ToggleLayoutModeCommand`&mdash;Triggers the RadPdfViewer LayoutModes (`ContinuousScroll` and `SinglePage`)
* `FitToWidthCommand`&mdash;There are two options when executing FitToWidth command:
	* `FitDocumentToWidthCommand`(the default one)&mdash;Refers to the whole document; it would lookup the widest of all pages and set a zoom level, so that this page is fit to width. 
	
		>tip If the document has pages with different width, as a side effect, when you are currently viewing a page that is not the widest, this page will not occupy the whole horizontal space.
		
	* `FitPageToWidthCommand`&mdash;It would execute fit to width on the current page disregarding the width of other pages from the document.

* `DoubleTappedCommand`&mdash;This command is different from the above listed as it is triggered from within the PdfViewer on double-tap action. On the first double-tap the document is zoomed 2.5 times at the tapped location, another double-tap triggers FitToWidth command.

>note PdfViewerToolbar contains some of the commands as built-in options, so you can use them though the predefined items in the Toolbar. For more information please check the [PdfViewer Toolbar]({%slug pdfviewer-toolbar%}) article.

## Example

Following is an example how the RadPdfViewer commands could be called on a button click action. 

>The snippet below shows one of the approaches for loading a pdf document inside PdfViewer just for the purpose of the example.

**1.** Add a pdf document to the project and set its build action to be `EmbeddedResource`.

**2.** Add the following code to visualize the document:

<snippet id='pdfviewer-commands'/>

**3.** Use the following snippet to declare a RadPdfViewer in XAML and add a few buttons that will execute the pdf viewer commands:

<snippet id='pdfviewer-commands-xaml'/>


By default `FitToWidth` command of the PdfViewer is assigned to "Fit Document to Width" option. You can easily switch to "Fit Page to Width" option by setting `FitToWidthCommand` property of RadPdfViewer to `FitPageToWidthCommand`, check the snippet below:
	
```C#	
this.pdfViewer.FitToWidthCommand = new FitPageToWidthCommand();
```

Calling the `FitToWidthCommand` on a button click action, as in the example above, executes "Fit Page to Width" on the current page.
 
> For the PdfViewer Commands example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to PdfViewer -> Commands category.

## See Also

- [PdfViewer Toolbar]({%slug pdfviewer-toolbar%})
