---
title: Configuration
page_title: .NET MAUI PDF Viewer Documentation - Configuration
description: Learn how to configure the search options, search results in the PDF Viewer for .NET MAUI.
position: 0
slug: pdfviewer-search-configuration
---

# .NET MAUI PDF Viewer Overview

The Telerik UI for .NET MAUI PDF Viewer exposes `SearchSettings` property which you can use to configure the search functionality, such as search criteria, commands, highlight colors, etc.

This section lists the properties of the `SearchSettings`, so you can customize it per your needs.

## Searching Text

Through the `Text` property of the `SearchSettings` you can retrieve or explicitly set the search text (in case you prefer not using the built-in search UI).

## Searching Options

Define search criterie by using the `SearchOptions` (of type `Telerik.Windows.Documents.Fixed.Search.TextSearchOptions`) and is used to define some search criteria as listed below:

* `UseRegularExpression`&mdash;Specifies whether a regular expression is used for searching.
* `CaseSensitive`&mdash;Indicates whether the search can be case sensitive.
* `WholeWordsOnly`&mdash;Indicates whether only whole words can be matched.

## Highlighting Colors

`SearchSettings` exposes two `Color` properties&mdash;`MainSearchResultFill` and `SearchResultsFill`. When a search is initiated, the found search results are highlighted. Two highlight colors are needed, as exactly one of all results has the MainSearchResultFill and is considered to be the main-result. This is for navigation purposes, so that a user will be able to navigate to previous and next results and keep track. The rest of the results are colored in the `SearchResultsFill`.

Here is an example of how you can customize `SearchOptions` as well as highlight colors:


## Searching Results

You can get the search results by using the following properties: 

* `SearchResultsStringFormat` (`string`)&mdash; The string format displays search results in `Telerik.Maui.Controls.PdfViewer.PdfViewerSearchContentView`. The default value is `{0}{1}{2}` which results in strings like `'1 of 5'`, where `'1'` means the first result is currently selected - `' of '` is a localizable string - `'5'` is the total number of search results.

* `TextSearchResult` property of the `SearchSettings` retrieves the current search result. It contains all the results that are found and as well as the main result. Main result is highlighted differently from the other search results and is used for navigation purposes, so that the user will be able to navigate to previous and next results and keep track.
The `TextSearchResult` exposes the following properties:
* static `TextSearchResult.NotFound` property&mdash;Returned in case there are no results per the search criteria;
* `SearchResults`&mdash;Read-only collection of type `Telerik.Windows.Documents.Fixed.Search.SearchResult` which contains all the search results.
* `MainSearchResult`&mdash;A reference to the search result considered as main result.

## See Also

- [.NET MAUI PDF Viewer Product Page](https://www.telerik.com/maui-ui/pdfviewer)
- [.NET MAUI PDF Viewer Forum Page](https://www.telerik.com/forums/maui?tagId=2059)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
