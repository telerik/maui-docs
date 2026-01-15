---
title: Overview
page_title: Telerik UI for .NET MAUI AI Tooling Overview
description: Learn about the AI-powered developer tools that integrate with your IDE or code editor for greater productivity and enhanced developer experience.
slug: ai-overview
tags: telerik,maui,dotnetmaui,ai,coding assistant
position: 0
---

# Telerik UI for .NET MAUI AI Coding Assistant

The Telerik UI for .NET MAUI AI Coding Assistant enhances your developer experience and increases productivity when building .NET MAUI applications with Telerik UI for .NET MAUI components.

The coding assistant is an AI code generator that provides specialized context to AI models, enabling them to produce higher-quality code samples using the [Telerik UI for .NET MAUI components](https://www.telerik.com/maui-ui) and APIs.

## Available Tools

The Telerik AI Coding Assistant is integrated in the [Telerik MAUI MCP Server]({%slug ai-mcp-server%})

| Feature                | MCP Server                                                                |
|------------------------|---------------------------------------------------------------------------|
| Prompt Handling        | Handles complex, multi-step prompts                                       |
| Client Compatibility   | Works with MCP-enabled clients (e.g., Cursor, Copilot Agent mode)         |
| Code Suggestions       | Can directly suggest changes and rebuild applications to verify code      |
| Response Focus         | Primarily code-focused                                                    |

## Getting Started

To use the Telerik MAUI AI Coding Assistant, you need:

@[template](/_contentTemplates/common/ai-coding-assistant.md#getting-started)
* @[template](/_contentTemplates/common/ai-coding-assistant.md#number-of-requests)

To learn how to set up and use the Telerik MAUI AI Coding Assistant, see the [Getting Started with the Telerik UI for .NET MAUI AI Coding Assistant]({%slug ai-mcp-server%}) article.

## Intended Use

You can use the Telerik AI Coding Assistant for:

* Initial code generation&mdash;Quickly add components to your app to speed up the initial development.
* Component configuration&mdash;Enable or disable specific component features, or fine tune the configuration through prompting. More complex configurations are possible but may require additional manual work to be production-ready.
* Dummy data generation and data binding&mdash;Quickly add data to your app for testing and prototyping purposes. Avoid exposing or providing access to your proprietary or production data to AI-enabled tools.
* Step-by-step explanations&mdash;Understand the solutions provided by the AI Coding Assistant through the detailed explanations (depends on the tool, mode, and model). To further develop your knowledge, check the respective documentation.
* Preliminary troubleshooting&mdash;Resolve obvious and easy-to-solve issues affecting your code. For more complex issues, search the product documentation or look for assistance from the community.

>warning Always double-check the suggested code and solutions of any AI-powered tool before applying them to your app.

## Recommendations

Consider the following recommendations when working with the AI Coding Assistant:

* Add NuGet packages/referenced assemblies for the Telerik UI for MAUI product.
* Set the `.sln` as a context.
* When switching between tasks and files, start a new session in a new chat window to avoid polluting the context with irrelevant or outdated information.
* At the time of publishing, Claude Sonnet 4 produces optimal results.

## Telerik Document Processing AI Coding Assistant

You can also use the AI Coding Assistant for Telerik Document Processing to generate high-quality code samples and speed up your development.
Read the full guide in the dedicated [DPL AI Coding Assistant article](https://docs.telerik.com/devtools/document-processing/ai-coding-assistant/overview).

## Usage Limits

Access to the AI Coding Assistant depends on your [Telerik license type](https://www.telerik.com/purchase/faq/licensing-purchasing):

### Subscription Licenses

* A Subscription is the primary license that grants full access to the AI Coding Assistant.
* Includes a virtually unlimited number of requests, with fair usage applied

### Perpetual Licenses

* Perpetual license holders have no access to the AI Coding Assistant by default.
* You can start a [30-day trial](https://www.telerik.com/try/ui-for-maui) to access the AI Coding Assistant.
* After the trial expires, access is no longer available unless the [Perpetual license is converted to a Subscription license](https://www.telerik.com/account/support-center/contact-us/account-support).

### Trial Licenses

* A [Telerik UI for .NET MAUI trial](https://www.telerik.com/try/ui-for-maui) automatically starts a 30-day trial for the AI tools.
* Trial licenses grant access to the AI Coding Assistant.
* The number of requests is virtually unlimited, with fair use policy applied.
* Reactivating the same trial for a new release does not grant additional requests.
* Designed for evaluating the feature before purchasing.

> All Telerik AI tools share a single request quota for your Telerik account. Complex prompts in the MCP server may consume multiple requests.
> When using the Telerik MCP server, one prompt may trigger several requests, depending on the prompt complexity.

## Privacy

The Telerik MAUI AI Coding Assistant operates under strict privacy guidelines:

Data Access:
* No access to your workspace and application code.
* Exception: when using the Telerik MCP server (or any other MCP server), the LLM generates parameters for the MCP server request, which may include parts of your application code.

Data Usage:
* Your prompts are not used to train Telerik AI models.
* Does not generate or access AI responses.
* Provides enhanced context to improve responses from your chosen AI model (GPT, Gemini, Claude, etc.).

Data Storage:
* Prompts and context are anonymized and stored only for statistical analysis and troubleshooting.
* No association between prompts and your Telerik user account.
* Usage metrics are collected to ensure [license compliance](#number-of-requests).

> Make sure also to review the terms and privacy policies of your selected AI model and AI client.

## Next Steps

* Configure the [Telerik MAUI MCP Server]({%slug ai-mcp-server%}) with an MCP-enabled client
* Review the [Prompt Library]({%slug ai-prompt-library%})