---
title: Commands
page_title: .NET MAUI PDF Viewer Documentation - Commands
description: Check out the commands provided by the Telerik UI for .NET MAUI PDF Viewer control.
position: 13
slug: pdfviewer-commands
---

# Commands

The <a href="https://www.telerik.com/maui-ui/pdf-viewer" target="_blank">.NET MAUI PDF Viewer</a> provides the following commands of type `ICommand`:

* `ZoomInCommand`&mdash;Zooms in.
* `ZoomOutCommand`&mdash;Zooms out.
* `NavigateToNextPageCommand`&mdash;Navigates to next page.
* `NavigateToPreviousPageCommand`&mdash;Navigates to previous page.
* `NavigateToPageCommand`&mdash;Navigates to a concrete page.
* `ToggleLayoutModeCommand`&mdash;Triggers the `RadPdfViewer` `LayoutModes` (`ContinuousScroll` and `SinglePage`).
* `FitToWidthCommand`&mdash;There are two options when executing `FitToWidth` command:
	* `FitDocumentToWidthCommand`(default)&mdash;Refers to the entire document; this option will look up the widest of all pages and set a zoom level allowing this page's width to fit. 
	
		>tip If the document has pages with different widths, when you view a page that is not the widest, this page will not occupy all available horizontal space.
		
	* `FitPageToWidthCommand`&mdash;Executes the `FitToWidth` command for the current page and disregards the width of the other pages in the document.

* `DoubleTappedCommand`&mdash;This command is triggerd by the user when double-tapping the content area of the PDF Viewer. On the first double-tap, the document is zoomed 2.5 times at the tapped location, another double-tap triggers the `FitToWidth` command.

>note PDF Viewer's toolbar contains some of the commands as built-in options so you can use them though the predefined items in the toolbar. For more information, check the [PDF Viewer Toolbar]({%slug pdfviewer-toolbar%}) article.

## Example: Using the PDF Viewer Commands

The following example shows how to call `RadPdfViewer` commands on a button click action. The snippet below shows only one of the available approaches for loading a PDF document.

**1.** Add a PDF document to the project and set its build action to `EmbeddedResource`.

**2.** Add the following code to visualize the document:

<snippet id='pdfviewer-commands'/>

**3.** Use the following snippet to declare a `RadPdfViewer` in XAML and add a few buttons that will execute the PDF Viewer commands:

<snippet id='pdfviewer-commands-xaml'/>


By default , the `FitToWidth` command of the PDF Viewer is assigned to the "Fit Document to Width" option. To switch to the "Fit Page to Width" option, set the `FitToWidthCommand` property of `RadPdfViewer` to `FitPageToWidthCommand`:
	
```C#	
this.pdfViewer.FitToWidthCommand = new PdfViewerFitPageToWidthCommand();
```

Calling the `FitToWidthCommand` on a button click action, as in the example above, executes "Fit Page to Width" on the current page.
 
> For a runnable example demonstrating the PDF Viewer commands, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **PdfViewer > Commands**.

## See Also

- [PdfViewer Toolbar]({%slug pdfviewer-toolbar%})
