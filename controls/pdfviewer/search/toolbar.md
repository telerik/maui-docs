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
* `PdfViewerSearchNavigationToolbarItem`&mdash;Represents a button item which activates the search functionality in PDF Viewer. This toolbar create a default set of toolbar items within the currently displayed toolbar item. This toolbar item is mainly developed for desktop. Still you can use it on mobile.

By default the items are autopopulated. You can disable this by setting the `AutoGenerateItems` to `false`.

* `PdfViewerSearchToolbarItem`&mdash;Represents a button item which activates the search functionality in PDF Viewer. This toolbar create a default set of toolbar items within the currently displayed toolbar item. This toolbar item is mainly developed for desktop. Still you can use it on mobile.

>note If the text in the entry is cleared, the search results will be cleared as well.

By default, search operation occurs when the user clicks the `Search` button of the keyboard on mobile, and the `Enter` key of the physical keyboard on desktop. You can modify this behavior by setting the `TextSearchTrigger` property of the `SearchSettings`. `TextSearchTrigger` is an enum of type `Telerik.Maui.Controls.PdfViewer.PdfViewerSearchTrigger`, and you can use it to define when a search operation can be performed. The available options are:

* `None`&mdash;Programmatically calls the search operation.
* `TextChanged`&mdash;Search is triggered every time the Text is changed.
* `Completed` (default)&mdash;Search operation is triggered when the corresponding entry completes (by pressing Enter/Return key).

## See Also

- [.NET MAUI PDF Viewer Product Page](https://www.telerik.com/maui-ui/pdfviewer)
- [.NET MAUI PDF Viewer Forum Page](https://www.telerik.com/forums/maui?tagId=2059)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
