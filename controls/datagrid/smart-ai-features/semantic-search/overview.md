---
title: AI Semantic Search
page_title: .NET MAUI DataGrid Documentation - AI Semantic Search
description: Learn how to use the AI Semantic Search feature in the .NET MAUI DataGrid to find results based on conceptual similarity rather than exact keyword matching.
position: 1
slug: datagrid-ai-semantic-search-overview
---

# AI Semantic Search in .NET MAUI DataGrid

The .NET MAUI DataGrid provides an AI semantic search feature that goes beyond traditional keyword matching. Unlike the standard text search, which looks for exact or partial text matches, the AI semantic search uses vector embeddings to match results based on conceptual similarity. This means users can find relevant data even when the search query doesn't contain the exact words present in the DataGrid cells.

For example, searching for "food" can match a row containing "Snacks" or "pizza, pretzels, popcorn" because the terms are semantically related.

> AI semantic search requires an external AI embedding service (such as **OpenAI**, **Azure AI**, or a local **ONNX** model) to compute vector similarity.

## Key Features

- **AI Search View integration**&mdash;Works with the DataGrid's AI Search View, which provides a UI for switching between text search and semantic search modes.
- **Conceptual matching**&mdash;Finds results based on meaning rather than exact text, improving relevance for natural-language queries.
- **Custom matching logic**&mdash;You control the matching through the `ProvideSearchMatchesAction` callback, allowing integration with any AI embedding service.
- **Filtering support**&mdash;Optionally hides non-matching rows by setting the `ApplyFilter` property.
- **Events**&mdash;Provides `SearchStarting` and `SearchCompleted` events for intercepting and reacting to search operations.

## How Semantic Search Works

The semantic search flow involves the following steps:

1. The user enters a search query (through the `SearchText` property or the AI Search View).
2. The DataGrid iterates over each cell and invokes the `ProvideSearchMatchesAction` callback, passing a `DataGridSemanticSearchCellProbe` instance.
3. The callback evaluates whether the cell value is semantically related to the search query (using an AI embedding service or custom logic) and sets the `IsMatch` property on the probe.
4. The DataGrid highlights or filters the matching rows based on the results.

## Getting Started with Semantic Search

To enable semantic search in the DataGrid, follow these steps:

1. Set the DataGrid's `IsAIEnabled` property to `true`.

2. Define the DataGrid in XAML with `SemanticSearchSettings` and `AISettings`:

<snippet id='datagrid-semantic-search-xaml' />

3. Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

4. Set the `ProvideSearchMatchesAction` callback to supply the semantic matching logic:

<snippet id='datagrid-semanticsearch-provide-search-matches' />

5. Implement the matching method. The method receives a `DataGridSemanticSearchCellProbe` and sets `IsMatch` to `true` for cells that satisfy the semantic search criteria:

<snippet id='datagrid-semanticsearch-provide-search-matches-method' />

> In a real application, replace the local matching logic with a call to an AI embedding service (such as OpenAI, Azure AI, or a local ONNX model) that computes vector similarity between the search query and the cell text.

6. (Optional) Handle the `SearchStarting` and `SearchCompleted` events:

<snippet id='datagrid-semantic-search-starting-event' />

<snippet id='datagrid-semanticsearch-completed' />

7. Define the data model:

<snippet id='datagrid-semantic-search-product' />

8. Define the ViewModel:

<snippet id='datagrid-semantic-search-viewmodel' />

>tip For a runnable example demonstrating the AI Semantic Search with mock service, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **DataGrid > Search** category.

## Using Semantic Search with AI Model

The DataGrid's AI Search View provides a built-in UI that allows users to switch between text search and semantic search modes. To enable semantic search as the default mode:

1. Set the DataGrid's `IsAIEnabled` property to `true`.
2. Configure the `AISettings` property with `ViewMode` set to `Search` and `SearchMode` set to `SemanticSearch`.
3. Use the `ProvideSearchMatchesAction` to specify search matches based on custom logic.
4. Configure an appropriate AI embedding service (such as OpenAI, Azure AI, or a local ONNX model) to compute vector similarity for semantic search.

>tip For a runnable example demonstrating the Semantic Search with AI model, see the [Controls Samples Demo Application]({%slug controls-samples-app%}) and go to the **DataGrid** category.

## See Also

- [AI Smart Assistant Overview]({%slug datagrid-ai-prompt-overview %})
- [Configure the AI Smart Assistant]({%slug datagrid-ai-prompt-configuration %})
