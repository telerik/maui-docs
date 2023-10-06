---
title: Toolbar Items
page_title: .NET MAUI PDF Viewer Documentation - Toolbar Items
description: Learn more for the available toolbar items for search functionality in Telerik .NET MAUI PDF Viewer. 
position: 0
slug: pdfviewer-search-overview
---

# .NET MAUI PDF Viewer Search Toolbar items

PDF Viewer provides built-in support for text searching. Through the exposed commands related to search operation, namely `OpenSearchViewCommand`, `CloseSearchViewCommand`, `NavigateToNextSearchResultCommand`, and `NavigateToPreviousSearchResultCommand` users can manipulate the search toolbar behavior.

In addition, `RadPdfViewerToolbar` exposes predefined toolbar items wired to the search. 

* `PdfViewerNavigateToNextSearchResultToolbarItem`&mdash;Represents a button item which navigates to the next search result in the PDF Viewer control.
* `PdfViewerNavigateToPreviousSearchResultToolbarItem`&mdash;Represents a button item which navigates to the previous search result in the PDF Viewer control.
* `PdfViewerSearchBusyIndicatorToolbarItem`&mdash;Represents a busy indicator whic is displayed while calculating the search results.
* `PdfViewerSearchEntryToolbarItem`&mdash;Represents an entry item to input search terms in the SearchToolbar.
* `PdfViewerSearchNavigationToolbarItem`&mdash;Represents a button item which activates the search functionality in PDF Viewer. This toolbar create a default set of toolbar items within the currently displayed toolbar item. The Toolbar items are:
By default the items are autopopulated. You can disable this by setting the `AutoGenerateItems` to `false`.


* `PdfViewerSearchToolbarItem`&mdash;Represents a button item which activates the search functionality in PDF Viewer. This toolbar create a default set of toolbar items within the currently displayed toolbar item. The Toolbar items are:


## Additional Toolbar Items for Hyperlink Operations

The `RichTextEditorHyperlinkNavigationToolbarItem` has the following items:

* `RichTextEditorEditHyperlinkToolbarItem`&mdash;Edits the hyperlink from the current selection.
* `RichTextEditorRemoveHyperlinkToolbarItem`&mdash;Removes the hyperlink from the current selection.
* `RichTextEditorOpenHyperlinkToolbarItem`&mdash;Navigates to the URL.

## See Also

- [.NET MAUI PDF Viewer Product Page](https://www.telerik.com/maui-ui/pdfviewer)
- [.NET MAUI PDF Viewer Forum Page](https://www.telerik.com/forums/maui?tagId=2059)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
