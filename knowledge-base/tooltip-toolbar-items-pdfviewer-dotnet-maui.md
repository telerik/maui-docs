---
title: Adding Tooltip to Toolbar Items in PDF Viewer for .NET MAUI
description: Learn how to define a tooltip with text for the toolbar items in PDF Viewer for .NET MAUI.
type: how-to
page_title: Define Tooltip for PDF Viewer Toolbar Items in .NET MAUI
meta_title: Define Tooltip for PDF Viewer Toolbar Items in .NET MAUI
slug: tooltip-toolbar-items-pdfviewer-dotnet-maui
tags: pdfviewer, .net-maui, tooltip, toolbaritems, buttontoolbaritemview, style, tooltipproperties.text
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | --- | ---- | 
| 11.0.0 | Telerik UI for .NET MAUI PDF Toolbar | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I want to add tooltips to the toolbar items in the PDF Viewer for .NET MAUI. How can I define a tooltip for the toolbar buttons?

This knowledge base article also answers the following questions:
- How to set tooltip text for toolbar buttons in PDF Viewer for .NET MAUI?
- How to customize tooltips in the PDF Viewer toolbar?
- How to apply tooltip properties to RadToolbar items?

## Solution

The PDF Viewer toolbar inherits from `RadToolbar`, which allows the use of tooltips for toolbar items. To define a tooltip for toolbar items, set the `Style` property with a `TargetType` as `ButtonToolbarItemView` and use the `ToolTipProperties.Text` property.

Here's an example:

```xml
<ContentPage.Resources>
	<ResourceDictionary>
		<Style x:Key="fitstyle" TargetType="telerik:ButtonToolbarItemView">
			<Setter Property="ToolTipProperties.Text" Value="My text" />
		</Style>
	</ResourceDictionary>
</ContentPage.Resources>

<Grid RowDefinitions="Auto, *">
	<telerik:RadPdfViewerToolbar OverflowMode="Scroll"
                             PdfViewer="{Binding Source={x:Reference pdfViewer}}">
		<telerik:PdfViewerFitToWidthToolbarItem Style="{StaticResource fitstyle}" />
		<telerik:PdfViewerZoomInToolbarItem />
		<telerik:PdfViewerZoomOutToolbarItem />
		<telerik:PdfViewerToggleLayoutModeToolbarItem />
		<telerik:PdfViewerNavigateToPreviousPageToolbarItem />
		<telerik:PdfViewerNavigateToNextPageToolbarItem />
		<telerik:PdfViewerNavigateToPageToolbarItem />
	</telerik:RadPdfViewerToolbar>
	<telerik:RadPdfViewer x:Name="pdfViewer" Grid.Row="1" />
</Grid>
```

## See Also
- [PDF Viewer for .NET MAUI](https://docs.telerik.com/devtools/maui/controls/pdfviewer/overview)
- [Toolbar Control](https://docs.telerik.com/devtools/maui/controls/toolbar/overview)
