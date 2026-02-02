---
title: Templates
page_title: .NET MAUI DataGrid Documentation - Templates
description: Learn how to override the built-in templates for the Prompt Controlled feature in the Telerik UI for .NET MAUI DataGrid component.
position: 13
slug: datagrid-ai-prompt-templates
---

# .NET MAUI DataGrid AI Smart Assistant Templates

The .NET MAUI DataGrid control allows you to override the built-in templates for the AI Smart Assistant feature to create a customized user experience.

Use the `AIViewTemplate` (`DataTemplate`) property on DataGrid level to override the default template for the DataGridAIPromptInput.

Use the `EmptyContentTemplate` (`DataTemplate`) property on `AISettings` level to override the default template for the empty content view displayed when there are no suggestions available.

>tip When having both templates defined, the `AIViewTemplate` takes precedence over the `EmptyContentTemplate`.

Here is an example of how to define custom templates for the AI Smart Assistant feature.

An example of `AIViewTemplate`:

<snippet id='datagrid-promptcontrolled-aiview-template' />

An example of `EmptyContentTemplate`:

<snippet id='datagrid-promptcontrolled-empty-template' />

## See also

- [Prompt Controlled Overview]({%slug datagrid-ai-prompt-overview %})
- [Style the AI Smart Assistant Templates]({%slug datagrid-ai-prompt-styling %})
- [Configure the AI Smart Assistant]({%slug datagrid-ai-prompt-configuration %})
