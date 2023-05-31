---
title: Viewport Settings
page_title: .NET MAUI PdfViewer Documentation - PdfViewer Viewport
description: Check our &quot;PdfViewer Viewport&quot; documentation article for Telerik PdfViewer for .NET MAUI control.
position: 3
slug: pdfviewer-viewport
published: False
---

# Viewport Settings

.NET MAUI PdfViewer provides API for getting and manipulating its viewport through the `Viewport` property and `ChangeViewport` method. 

The viewport is the "window" in which the PdfViewer displays its content, users can change the viewport through zooming, panning and scrolling:

![.NET MAUI PdfViewer Viewport](images/pdfviewer-viewport.gif)

In order to explain how the viewport works, first we need to make clear what's the PdfViewer content as well as how to define the content size. The PdfViewer content is the pdf document itself, and more specifically the document pages. PdfViewer provides two layout mode (`SinglePage` and `ContinuousScroll`) which use different approaches for arranging the document pages. The way the content is defined varies according to the selected layout mode.

>tip For detailed information on the available layout modes check [Viewing Modes]({%slug pdfviewer-key-features%}#viewing-modes) topic.

## LayoutModes

**SinglePage**

With `SinglePage` layout mode RadPdfViewer shows one page at a time (the pages are stacked), so the content is the current page and the content size is the size of that page. In cases there are pages with different size in the pdf document, the content size is changed accordingly. 

The viewport position is calculated relative to the current page.

![.NET MAUI PdfViewer SinglePage LayoutMode](images/pdfviewer-viewport-singlepage.png)

**ContinuousScroll**

With ContinuousScroll layout mode, the content refers to all pages of the document. In this mode the pages are ordered vertically one below another with space between them and are horizontally centered (if the document contains pages with different width, some pages will not be at 0 horizontal position). 

The content width is even to the widest page. The content height is calculated as a sum of the heights of all the pages plus a sum of the distances between the pages (the distance between pages is controlled by the `PageSpacing` property of the PdfViewer).

So, the viewport position is calculated relative to the whole content (all pages + distances):

![.NET MAUI PdfViewer ContinuousScroll LayoutMode](images/pdfviewer-viewport-continuous.png)

No matter which layout mode is selected, the viewport is the "window" which moves over the defined content and renders those pdf elements currently positioned in it.

The `Viewport` property of the PdfViewer is of type *Xamarin.Forms.Rectangle* and can be defined by its top left corner at (x, y) position and width and height values. Keep in mind it's possible to have negative X and Y values in case the viewport becomes bigger than the content itself.

## Example

The example below demonstrates how you can utilize the `ChangeViewport` method to navigate to the last page of the document in `ContinuousScroll` and `SinglePage` layout modes as well as how to access the current viewport.

Use the following snippet to define the RadPdfViewer and RadPdfToolbar:

```XAML
<Grid>
	<Grid.RowDefinitions>
		<RowDefinition Height="Auto"/>
		<RowDefinition />
	</Grid.RowDefinitions>
	<telerikPdfViewer:RadPdfViewerToolbar PdfViewer="{Binding Source={x:Reference pdfViewer}}">
		<telerikPdfViewer:ZoomInToolbarItem />
		<telerikPdfViewer:ZoomOutToolbarItem />
		<telerikPdfViewer:NavigateToNextPageToolbarItem/>
		<telerikPdfViewer:NavigateToPreviousPageToolbarItem/>
		<telerikPdfViewer:NavigateToPageToolbarItem/>
		<telerikPdfViewer:FitToWidthToolbarItem/>
		<telerikPdfViewer:ToggleLayoutModeToolbarItem/>
	</telerikPdfViewer:RadPdfViewerToolbar>
	<telerikPdfViewer:RadPdfViewer x:Name="pdfViewer" Grid.Row="1"/>
</Grid>
```

In addition to this, you need to add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

In order to get the current viewport  position and size, use the snippet below:

<snippet id='pdfviewer-viewport-getviewport' />

The next snippets demonstrates how you can manipulate the viewport of the PdfViewer:

<snippet id='pdfviewer-viewport-setviewport' />

## See Also

- [Commands]({%slug pdfviewer-commands%})
