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

Define search criteria by using the `SearchOptions` (of type `Telerik.Windows.Documents.Fixed.Search.TextSearchOptions`) and used to define some search criteria as listed below:

* `UseRegularExpression`&mdash;Specifies whether a regular expression is used for searching.
* `CaseSensitive`&mdash;Indicates whether the search can be case sensitive.
* `WholeWordsOnly`&mdash;Indicates whether only whole words can be matched.

## Triggering Search

By default, search operation occurs when the user clicks the `Search` button of the keyboard on mobile, and the `Enter` key of the physical keyboard on desktop. You can modify this behavior by setting the `TextSearchTrigger` property of the `SearchSettings`. `TextSearchTrigger` is an enum of type `Telerik.Maui.Controls.PdfViewer.PdfViewerSearchTrigger`, and you can use it to define when a search operation can be performed. The available options are:

* `None`&mdash;Programmatically calls the search operation.
* `TextChanged`&mdash;Search is triggered every time the Text is changed.
* `Completed` (default)&mdash;Search operation is triggered when the corresponding entry completes (by pressing Enter/Return key).

## Highlighting Colors

`SearchSettings` exposes two `Color` properties&mdash;`MainSearchResultFill` and `SearchResultsFill`. When a search is initiated, the found search results are highlighted. Two highlight colors are needed, one of all results has the `MainSearchResultFill` and is considered to be the main-result. This is for navigation purposes, so that a user can navigate to previous and next results and keep track. The rest of the results are colored in the `SearchResultsFill`.

Here is an example of how you can customize `SearchOptions` as well as highlight colors:

<snippet id='pdfviewer-search-settings' />


## Searching Results

You can get the search results by using the following properties: 

* `SearchResultsStringFormat` (`string`)&mdash; The string format displays search results in `Telerik.Maui.Controls.PdfViewer.PdfViewerSearchContentView`. The default value is `{0}{1}{2}` which results in strings like `'1 of 5'`, where `'1'` means the first result is currently selected - `' of '` is a localizable string - `'5'` is the total number of search results.

```XAML
<telerik:RadPdfViewer x:Name="pdfViewer">
    <telerik:RadPdfViewer.SearchSettings>
        <telerik:PdfViewerSearchSettings SearchResultsStringFormat="Result: {0}, Total: {2}"/>
    </telerik:RadPdfViewer.SearchSettings>
</telerik:RadPdfViewer >
```

* `TextSearchResult` property of the `SearchSettings` retrieves the current search result. It contains all the results that matches the search as well as the main result. Main result is highlighted differently from the other search results and is used for navigation purposes, so that the user can navigate to previous and next results and keep track.
The `TextSearchResult` exposes the following properties:
	* static `TextSearchResult.NotFound` property&mdash;Is Returned when the search criteria has no results;
	* `SearchResults`&mdash;Read-only collection of type `Telerik.Windows.Documents.Fixed.Search.SearchResult` which contains all the search results.
	* `MainSearchResult`&mdash;A reference to the search result that are the main result.

## Methods

The Telerik UI for .NET MAUI PDF Viewer provides methods related to searching feature.

* `SearchAsync`&mdash;Starts an async search operation with the provided text and options.
* `GetToastInfoForToolbarItem`&mdash;Override this method to customize the text in the notification toast based on the search state. 

## See Also

- [.NET MAUI PDF Viewer Product Page](https://www.telerik.com/maui-ui/pdfviewer)
- [.NET MAUI PDF Viewer Forum Page](https://www.telerik.com/forums/maui?tagId=2059)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
