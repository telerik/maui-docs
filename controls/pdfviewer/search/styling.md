---
title: Styling
page_title: .NET MAUI PDF Viewer Documentation - Styling
description: Learn more about the styling options for the search toolbar items.
position: 6
slug: pdfviewer-search-styling
---

# .NET MAUI PDF Viewer Search Commands

The PDF Viewer for .NET MAUI provides a flexible styling API for its search toolbar items. 

As the `PDFViewerToolbar` is based on the `RadToolbar` control, all toolbar items in the PDF Viewer inherit from `ButtonToolbarItem`. All styling properties available for the `ButtonToolbarItem` are also applicable for the PDF toolbar items. 

The table below lists all toolbar items related to the search feature and their target type:

| Toolbar Item | Target Type |
| ------ | ------ |
| `PdfViewerSearchNavigationToolbarItem` | `Style` property with target type `NavigationButtonToolbarItemView`  |
| `PdfViewerNavigateToPreviousSearchResultToolbarItem` | `Style` property with target type `PdfViewerNavigateToPreviousSearchResultToolbarItemView` |
| `PdfViewerNavigateToNextSearchResultToolbarItem` | `Style` property with target type `PdfViewerNavigateToNextSearchResultToolbarItemView` |
| `PdfViewerSearchEntryToolbarItem` | `Style` property with target type `PdfViewerSearchEntryToolbarItemView` |
| `PdfViewerSearchBusyIndicatorToolbarItem` | `Style` property with target type `PdfViewerSearchBusyIndicatorToolbarItemView` |

The `PdfViewerSearchBusyIndicatorToolbarItemView` inherits from the [BusyIndicatorToolbarItemView]({%slug toolbar-items-busyindicator%}) article.

The `PdfViewerSearchEntryToolbarItemView` inherits from the [EntryToolbarItemView]({%slug toolbar-items-entry%}) article.

The `PdfViewerNavigateToPreviousSearchResultToolbarItemView`, `PdfViewerNavigateToNextSearchResultToolbarItemView`, and `NavigationButtonToolbarItemView` inherit from [ButtonToolbarItemView]({%slug toolbar-items-button%}). 

## Styling the Search Toast Message on Mobile

The `PdfViewerSearchNavigationToolbarItem` has a `ToastStyle` property which allows you to style the toast message with search results on mobile. The target type of the `ToastStyle` is the `PdfViewerSearchToast`.

Here is an example how to define the `ToastStyle`

<snippet id='prfviewer-search-toast' />

And the `PdfViewerSearchNavigationToolbarItem`:

<snippet id='pdfviewer-search-toast-style' />

## Styling the Search Settings

The search results are highlighted by using the following properties:

* `MainSearchResultFill` (`Color`)&mdash;Specifies the fill of the main search result.
* `SearchResultsFill` (`Color`)&mdash;Specifies the fill of all search results, except the main result.

## See Also

- [.NET MAUI PDF Viewer Forum Page](https://www.telerik.com/forums/maui?tagId=2059)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
