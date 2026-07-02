---
title: Configuration
page_title: .NET MAUI DataGrid Documentation - Configuration
description: Learn how to configure the .NET MAUI DataGrid AI Semantic Search.
position: 2
slug: datagrid-ai-semantic-search-configuration
---

# Configure the AI Semantic Search in .NET MAUI DataGrid

This article provides information on how to configure the AI Semantic Search functionality in the .NET MAUI DataGrid control.

## Semantic Search Settings

Configure the semantic search through the `SemanticSearchSettings` property of the `RadDataGrid`. The `DataGridSemanticSearchSettings` class inherits from `DataGridSearchSettingsBase` and exposes the following key members:

* `SearchText` (`string`)&mdash;Defines the search text. Before a search starts, this value is trimmed, and the `SearchStarting` event is raised allowing you to change the effective search text.
* `IntermediateSearchText` (`string`)&mdash;Specifies the text of the search entry. Changes to this value do not necessarily trigger a search&mdash;the `SearchText` property is updated according to the `SearchTrigger` property.
* `ProvideSearchMatchesAction` (`Action<DataGridSearchProbe>`)&mdash;Specifies the callback invoked for each cell to determine semantic matches. The callback receives a `DataGridSemanticSearchCellProbe` instance.
* `ApplyFilter` (`bool`)&mdash;Specifies a value indicating whether rows that do not match the search criteria are filtered out.
* `SearchTrigger` (`DataGridSearchTrigger`)&mdash;Specifies when a search operation is performed&mdash;`TextChanged` (default) triggers on every keystroke, `Completed` triggers on `Enter`/`Return` key.

## Semantic Search Cell Probe

When the `ProvideSearchMatchesAction` callback is invoked, it receives a `DataGridSemanticSearchCellProbe` object. This probe provides the following properties:

* `SearchText` (`string`)&mdash;Gets the semantic-search text that should be searched for.
* `Column` (`DataGridColumn`)&mdash;Gets the column for the cell that exploration for search matches is performed.
* `CellValue` (`object`)&mdash;Gets the value of the cell being evaluated.
* `IsMatch` (`bool`)&mdash;Specifies whether the cell is a semantic match. Setting this to `true` adds the cell to the search results.
* `Item` (`object`)&mdash;Gets the data item (business object) associated with the current row.
* `ItemText` (`string`)&mdash;Gets the text displayed in the DataGrid.
* `Matches` (`List<DataGridSearchMatch>`)&mdash;Gets a collection of search matches for the associated item.
* `CancellationToken` (`CancellationToken`)&mdash;A token that is canceled when the current search operation is canceled.

## Events

The `DataGridSemanticSearchSettings` class provides the following events:

* `SearchStarting`&mdash;Raised before searching starts. The `SearchStarting` event handler receives the following parameters: 
    * The `sender` argument, which is of type `object`.
    * `DataGridSearchStartingEventArgs` object. The `DataGridSearchStartingEventArgs` provides the following properties:
        * `SearchTerms` (`IList<string>`)&mdash;Gets or sets the search terms to search for.
        * `SearchTermsLogicalOperator` (`LogicalOperator`)&mdash;Gets or sets the logical operator used when more than one search term is present.
        * `Cancel` (`bool`)&mdash;Gets or sets a value indicating whether to cancel the search.

* `SearchCompleted`&mdash;Raised after searching is completed. The `SearchCompleted` event handler receives the following parameters:
    * The `sender` argument, which is of type `object`.
    * An `EventArgs` object.

## AISettings and Semantic Search Properties

Use the following properties from the AI Settings to configure the Semantic Search functionality in the DataGrid:

* `ViewMode` (`DataGridAIViewMode`)&mdash;Specifies the view mode of the AI Smart Assistant. The options are `Search` and `AIAssistant`.
* `Placeholder` (`string`)&mdash;Specifies the placeholder text for the search input field.
* `SearchMode` (`DataGridAISearchMode`)&mdash;Specifies the search mode of the AI Assistant. The options are `TextSearch` and `SemanticSearch`.
* `RecentTextSearches` (`IEnumerable<string>`)&mdash;Specifies the collection of recent keyword searches.
* `RecentSemanticSearches` (`IEnumerable<string>`)&mdash;Specifies the collection of recent semantic searches.
* `IsTextSearchOptionVisible` (`bool`)&mdash;Specifies whether the keyword search mode is enabled. The default value is `true`.
* `IsSemanticSearchOptionVisible` (`bool`)&mdash;Specifies whether the semantic search mode is enabled. The default value is `true`.
* `AreRecentTextSearchesVisible` (`bool`)&mdash;Specifies whether the recent keyword searches are visible. The default value is `true`.
* `AreRecentSemanticSearchesVisible` (`bool`)&mdash;Specifies whether the recent semantic searches are visible. The default value is `true`.
* `SearchDebounceDelay` (`TimeSpan`)&mdash;Specifies the delay before a search is triggered after the user stops typing. The default value is `500ms`.

To hide the AI Smart Assistant functionality, set the `IsSuggestedPromptsVisible` and `IsRecentPromptsVisible` properties to `false`.

## See Also

* [AI Semantic Search Overview]({%slug datagrid-ai-semantic-search-overview %})
* [AI Smart Assistant Overview]({%slug datagrid-ai-prompt-overview %})