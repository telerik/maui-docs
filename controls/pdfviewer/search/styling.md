---
title: Styling
page_title: .NET MAUI PDF Viewer Documentation - Styling
description: Learn more about the styling options for the search toolbar items.
position: 6
slug: pdfviewer-search-styling
---

# .NET MAUI PDF Viewer Search Styling

The <a href="https://www.telerik.com/maui-ui/pdf-viewer" target="_blank">.NET MAUI PDF Viewer</a> provides a flexible styling API for its search toolbar items. 

As the `PDFViewerToolbar` is based on the `RadToolbar` control, all toolbar items in the PDF Viewer inherit from `ButtonToolbarItem`. All styling properties available for the `ButtonToolbarItem` are also applicable for the PDF toolbar items. 

## Styling the Toolbar's Search Item on Mobile

The default search toolbar item displayed on mobile devices is the `PdfViewerSearchNavigationToolbarItem` (`Style` property with target type `NavigationButtonToolbarItemView`). The 

The table below lists all toolbar items related to the `PdfViewerSearchNavigationToolbarItem` and their target types:

| Toolbar Item | Target Type |
| ------ | ------ |
| `PdfViewerNavigateToPreviousSearchResultToolbarItem` | `Style` property with target type `PdfViewerNavigateToPreviousSearchResultToolbarItemView` |
| `PdfViewerNavigateToNextSearchResultToolbarItem` | `Style` property with target type `PdfViewerNavigateToNextSearchResultToolbarItemView` |
| `PdfViewerSearchEntryToolbarItem` | `Style` property with target type `PdfViewerSearchEntryToolbarItemView` |
| `PdfViewerSearchBusyIndicatorToolbarItem` | `Style` property with target type `PdfViewerSearchBusyIndicatorToolbarItemView` |
| `BackNavigationButtonToolbarItemView` | `Style` property with target type `ButtonToolbarItemView` |

## Styling the Toolbar's Search Item on Desktop

The default search toolbar item displayed on desktop devices is the `PdfViewerSearchToolbarItem`. The toolbar item exposes the following properties:

* `Style` (target type `ButtonToolbarItemView`)&mdash;Specfies the style applied to the toolbar button that opens the search popup on desktop.
* `SearchContentViewStyle` (`Style` with a target type of `PdfViewerSearchContentView`)&mdash;Specifies the style applied to the search popup.

The table below lists all styling properties available in the `SearchContentViewStyle`:

| Toolbar Item | Target Type |
| ------ | ------ |
| `CloseButtonToolbarItemStyle` | `Style` property with target type `ButtonToolbarItemView`  |
| `PreviousSearchResultToolbarItemStyle` | `Style` property with target type `PdfViewerNavigateToPreviousSearchResultToolbarItemView` |
| `NextSearchResultToolbarItemStyle` | `Style` property with target type `PdfViewerNavigateToNextSearchResultToolbarItemView` |
| `SearchEntryToolbarItemStyle` | `Style` property with target type `PdfViewerSearchEntryToolbarItemView` |
| `BusyIndicatorToolbarItemStyle` | `Style` property with target type `PdfViewerSearchBusyIndicatorToolbarItemView` |
| `SearchResultsLabelToolbarItemStyle` | `Style` property with target type `LabelToolbarItemView` |

The next table lists the inheritance of the target types:

| Target Type | Inherits from |
| ------ | ------ |
| `PdfViewerSearchBusyIndicatorToolbarItemView` | [`BusyIndicatorToolbarItemView`]({%slug toolbar-items-busyindicator%}) |
| `PdfViewerSearchEntryToolbarItemView` | [`EntryToolbarItemView`]({%slug toolbar-items-entry%}) |
| `PdfViewerNavigateToPreviousSearchResultToolbarItemView` | [`ButtonToolbarItemView`]({%slug toolbar-items-button%}) |
| `PdfViewerNavigateToNextSearchResultToolbarItemView` | [`ButtonToolbarItemView`]({%slug toolbar-items-button%}) |
| `NavigationButtonToolbarItemView` | [`ButtonToolbarItemView`]({%slug toolbar-items-button%}) |

## Styling the Search Toast Message on Mobile

The `PdfViewerSearchNavigationToolbarItem` has a `ToastStyle` property which allows you to style the toast message with search results on mobile. The target type of the `ToastStyle` is the `PdfViewerSearchToast`.

Here is an example how to define the `ToastStyle`

<snippet id='pdfviewer-search-toast' />

And the `PdfViewerSearchNavigationToolbarItem`:

<snippet id='pdfviewer-search-toast-style' />

## Styling the Search Settings

The search results are highlighted by using the following properties:

* `MainSearchResultFill` (`Color`)&mdash;Specifies the fill of the main search result.
* `SearchResultsFill` (`Color`)&mdash;Specifies the fill of all search results, except the main result.

Here is an example with styling the `MainSearchResultFill` and `SearchResultsFill`:

```XAML
<telerik:RadPdfViewer x:Name="pdfViewer">
    <telerik:RadPdfViewer.SearchSettings>
        <telerik:PdfViewerSearchSettings MainSearchResultFill="#99FF7F7F"
                                         SearchResultsFill="#997FC9FF"/>
    </telerik:RadPdfViewer.SearchSettings>
</telerik:RadPdfViewer>
```

## See Also

- [.NET MAUI PDF Viewer Forum Page](https://www.telerik.com/forums/maui?tagId=2059)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
