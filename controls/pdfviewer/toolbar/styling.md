---
title: Styling
page_title: .NET MAUI PDF Viewer Documentation - Toolbar Styling
description: Learn how to style the Telerik PDF Viewer Toolbar items.
position: 7
slug: pdfviewer-toolbar-styling
---

# .NET MAUI PDF Viewer Toolbar Styling

The <a href="https://www.telerik.com/maui-ui/pdf-viewer" target="_blank">.NET MAUI PDF Viewer</a> provides a flexible styling API for its toolbar items. 

## Style the Toolbar Items

The `PDFViewerToolbar` is based on the `RadToolbar` control, so the toolbar items in the PDF Viewer use a `ToolbarItem`. 

Each toolbar item has a `Style` property and the target type of the property is the corresponding `ToolbarItemView`:

| Toolbar Item | Style Target Type |
| ------------ | ------- |
| `PdfViewerFitToWidthToolbarItem ` | `ButtonToolbarItemView` |
| `PdfViewerZoomInToolbarItem ` | `ButtonToolbarItemView` |
| `PdfViewerZoomOutToolbarItem ` | `ButtonToolbarItemView` |
| `PdfViewerSearchToolbarItem ` | `ButtonToolbarItemView` |
| `PdfViewerToggleLayoutModeToolbarItem ` | `ButtonToolbarItemView` |
| `PdfViewerNavigateToPreviousPageToolbarItem ` | `ButtonToolbarItemView` |
| `PdfViewerNavigateToNextPageToolbarItem ` | `ButtonToolbarItemView` |
| `PdfViewerNavigateToPageToolbarItem ` | `ToolbarItemView` |
| `PdfViewerSearchNavigationToolbarItem ` | `NavigationButtonToolbarItemView` |

All styling properties available for the target type [`ButtonToolbarItemView`]({%slug toolbar-items-button%}) are also applicable for the PDF toolbar items that use this target type. 

All properties applicable for [`NavigationButtonToolbarItemView`]({%slug toolbar-items-navigation-button%}) can be used for stlying the `PdfViewerSearchNavigationToolbarItem`.

## Example for Styling the Toolbar

**1.** PDF Viewer and Toolbar definitions in XAML:

<snippet id='pdfviewer-toolbar-styling-xaml'/>

**2.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.**: Define the style in the page's resources:

<snippet id='pdfviewer-toolbar-styling-resources'/>

**4.** Pass the document to the `PdfViewer.Source`:

<snippet id='pdfviewer-toolbar'/>

Here is the result on the image below:

![.NET MAUI PdfViewer ToolbarStyling](images/pdf-toolbar-styling.png)

## See Also

- [RadPdfProcessing library](https://docs.telerik.com/devtools/document-processing/libraries/radpdfprocessing/overview)
