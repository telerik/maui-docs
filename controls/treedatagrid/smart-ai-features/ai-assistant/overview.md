---
title: AI Smart Assistant
page_title: .NET MAUI TreeDataGrid Documentation - AI Smart Assistant
description: Learn how to interact with the .NET MAUI TreeDataGrid using the AI Smart Assistant to input prompts to perform operations like sorting, filtering, and column manipulation.
position: 1
slug: treedatagrid-ai-prompt-overview
---

# AI Smart Assistant in .NET MAUI TreeDataGrid

The .NET MAUI TreeDataGrid control offers AI-powered features that allow users to interact with the TreeDataGrid using natural language prompts. This functionality enables users to perform various operations such as sorting, grouping, filtering, and manipulating columns without needing to write code.

On mobile, the AI Smart Assistant panel can be accessed via a floating action button on the bottom-right corner of the TreeDataGrid. On desktop platforms, the AI Smart Assistant panel displays above the header area of the TreeDataGrid.

Here is how the AI Smart Assistant panel looks on desktop and the floating action button on mobile:

![.NET MAUI TreeDataGrid AI Smart Assistant Panel](images/treedatagrid-ai-prompt-overview.png)

Here is how the AI Smart Assistant panel looks on desktop and mobile when no suggestions are shown:

![.NET MAUI TreeDataGrid AI Smart Assistant Panel](images/treedatagrid-ai-prompt-suggestions.png)

## Supported Operations

The following operations can be performed using AI Smart Assistant:

@[template](/_contentTemplates/controls/ai-data-operations.md#ai-smart-assistant-operations)

## Getting Started with the AI Smart Assistant

To get started with the AI Smart Assistant functionality in the .NET MAUI TreeDataGrid, follow the steps:

@[template](/_contentTemplates/controls/ai-data-operations.md#getting-started-with-the-ai-smart-assistant)

### 2. Process TreeDataGrid AI Requests

@[template](/_contentTemplates/controls/ai-data-operations.md#process-requests)

1. Set the TreeDataGrid's `IsAIEnabled` property to `true`. When setting to `true`, the AI Smart Assistant panel gets enabled, allowing users to input prompts.

## Example Prompts

Here are some example prompts that users can use to interact with the TreeDataGrid:

@[template](/_contentTemplates/controls/ai-data-operations.md#example-prompts)

## Example with AI Smart Assistant

**1.** Add TreeDataGrid definition in XAML:

<snippet id='treedatagrid-ai-prompt-controlled' />

**2.** Add the `telerik` namespace:
 
`xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"`

**3.** Define the `DataGridUserCommand`:

<snippet id='datagrid-user-command' />

**4.** Add sample data model:

<snippet id='treedatagrid-data-model' />

**5.** Define the `ViewModel`:

<snippet id='treedatagrid-prompt-viewmodel' />

>important The TreeDataGrid AI Smart Assistant examples in the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) use a Telerik-hosted AI service for demonstration purposes only. 
>
>To use the AI Smart Assistant in your application, you must configure your own AI service.
>
>How to do that is described in the [Getting Started with the AI Smart Assistant]({%slug treedatagrid-ai-prompt-overview%}#getting-started-with-the-ai-smart-assistant) article.

>tip For a runnable example demonstrating the AI Smart Assistant, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **TreeDataGrid > AI Smart Assistant** category.

## See also

- [Style the AI Smart Assistant]({%slug datagrid-ai-prompt-styling %})
- [Configure the AI Smart Assistant]({%slug datagrid-ai-prompt-configuration %})
- [Templates for AI Smart Assistant]({%slug datagrid-ai-prompt-templates %})