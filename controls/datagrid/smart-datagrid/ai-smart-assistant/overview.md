---
title: AI Smart Assistant 
page_title: .NET MAUI DataGrid Documentation - AI Smart Assistant 
description: Learn how to interact with the .NET MAUI DataGrid using the AI Smart Assistant to input prompts to perform operations like sorting, grouping, filtering, and column manipulation.
position: 1
slug: datagrid-ai-prompt-overview
---

# AI Smart Assistant in .NET MAUI DataGrid

The .NET MAUI DataGrid control offers AI-powered features that allow users to interact with the DataGrid using natural language prompts. This functionality enables users to perform various operations such as sorting, grouping, filtering, and manipulating columns without needing to write code.

## Supported Operations

The following operations can be performed using AI Smart Assistant:

- **Sorting**&mdash;Users can sort the DataGrid by specifying the column and the sort direction (ascending or descending).
- **Grouping**&mdash;Users can group the DataGrid by one or more columns.
- **Filtering**&mdash;Users can filter the DataGrid based on specific criteria.
- **Column Manipulation**&mdash;Users can freeze, hide columns and more.

## Enable the AI Smart Assistant Functionality

To enable AI Smart Assistant functionality in the .NET MAUI DataGrid, you have to set the DataGrid's `IsAIEnabled` property to `true`. 

On mobile the AI Smart Assistant panel can be accessed via a floating action button on the bottom-right corner of the DataGrid. On desktop platforms, the AI Smart Assistant panel displays above the header area of the DataGrid.

## Visual Structure

![.NET MAUI DataGrid AI Smart Assistant Panel](images/datagrid-ai-prompt-panel.png)

## Example Prompts

Here are some example prompts that users can use to interact with the DataGrid:

- "Sort the data by the Name column in ascending order."
- "Group the data by the Category column."
- "Filter the data to show only items with a price greater than 100."
- To freeze a column use the `lock` keyword. For example: "Lock the Price column."

## Example with AI Smart Assistant  Enabled

**1.** Add DataGrid definition in XAML:

<snippet id='datagrid-prompt-controlled' />

**2.** Add the `telerik` namespace:
 
`xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"`

**3.** Add sample data model:

<snippet id='datagrid-prompt-model' />

**4.** Define the `ViewModel`:

<snippet id='datagrid-prompt-viewmodel' />

## See also

- [AI Smart Assistant Overview]({%slug datagrid-ai-prompt-overview %})
- [Style the AI Smart Assistant Templates]({%slug datagrid-ai-prompt-styling %})
- [Configure the AI Smart Assistant]({%slug datagrid-ai-prompt-configuration %})
- [Templates for AI Smart Assistant]({%slug datagrid-ai-prompt-templates %})