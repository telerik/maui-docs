---
title: Configuration
page_title: .NET MAUI DataGrid Documentation - Configuration
description: Learn how to configure the .NET MAUI DataGrid AI Smart Assistant.
position: 2
slug: datagrid-ai-prompt-configuration
---

# Configure the AI Smart Assistant in .NET MAUI DataGrid

This article provides information on how to configure the AI Smart Assistant  functionality in the .NET MAUI DataGrid control.

## AI Smart Assistant  Settings

@[template](/_contentTemplates/controls/ai-data-operations.md#ai-smart-assistant-settings)

![MAUI DataGrid empty Prompts View](images/datagrid-empty-view.png)

## Events

The DataGrid provides the following events related to AI Smart Assistant functionality:

@[template](/_contentTemplates/controls/ai-data-operations.md#ai-prompt-events)

## Commands

@[template](/_contentTemplates/controls/ai-data-operations.md#ai-prompt-commands)

## Example

Here is an example of how to configure the AI Smart Assistant  settings in the .NET MAUI DataGrid:

**1.** Add the DataGrid definition in XAML:

<snippet id='datagrid-prompt-controlled-configuration' />

**2.** Add the `telerik` namespace:
 
`xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"`

**3.** Add a sample data model:

<snippet id='datagrid-prompt-configuration-model' />

**4.** Define the data for the DataGrid `ItemsSource`:

<snippet id='datagrid-prompt-load-sample-data' />

**5.** Define the prompt handling properties:

<snippet id='datagrid-promptrequest-handling-view' />

**6.** Handle the `PromptRequest` event in the code-behind:

<snippet id='datagrid-promptrequest-handling' />

**7.** Handle the `CancelPromptRequest` event in the code-behind:

<snippet id='datagrid-cancel-promptrequest-handling' />

**8.** Add items to the suggested prompts collection:

<snippet id='datagrid-aiprompt-config-suggested-prompts-collection' />

**9.** Add items to the recent prompts collection:

<snippet id='datagrid-aiprompt-config-recent-prompts-collection' />

**10.** Assign the collections to the `AISettings`:

<snippet id='datagrid-aiprompt-config-assign-collections' />

**11.** Set the data to the DataGrid `ItemsSource`:

<snippet id='datagrid-prompt-load-sample-data-call' />

![.NET MAUI DataGrid Configuration AI Assistant](images/datagrid-configuration.gif)

>important The DataGrid AI Smart Assistant examples in the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) use a Telerik-hosted AI service for demonstration purposes only. 
>
>You have to configure your own AI service for the AI Smart Assistant to work in your application.
>
>How to do that is described in the [Getting Started with the AI Smart Assistant]({%slug datagrid-ai-prompt-overview%}#getting-started-with-the-ai-smart-assistant) article.

>tip For a runnable example demonstrating the configuration options, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **DataGrid > AI Smart Assistant** category.

## See also

- [Prompt Controlled Overview]({%slug datagrid-ai-prompt-overview %})
- [Style the AI Smart Assistant]({%slug datagrid-ai-prompt-styling %})
- [Templates for AI Smart Assistant]({%slug datagrid-ai-prompt-templates %})