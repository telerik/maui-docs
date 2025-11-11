---
title: Copilot Extension
page_title: Telerik MAUI GitHub Copilot Extension
description: Learn how to add and use the Telerik MAUI GitHub Copilot extension as a .NET MAUI AI coding assistant and code generator for better developer productivity. The Telerik MAUI GitHub Copilot extension provides proprietary context about Telerik UI for .NET MAUI to AI-powered software.
slug: ai-copilot-extension
tags: telerik, maui, ai, dotnetmaui, coding assistant, ai server
position: 4
---

# Telerik MAUI GitHub Copilot Extension

The Telerik MAUI [GitHub Copilot](https://github.com/features/copilot) extension is an AI-powered coding assistant that provides specialized knowledge about [Telerik UI for .NET MAUI components](https://www.telerik.com/maui-ui). 

>caution [Microsoft is sunsetting GitHub Copilot extensions](https://github.blog/changelog/2025-09-24-deprecate-github-copilot-extensions-github-apps/) on November 10th, 2025, in favor of the Model Context Protocol (MCP) standard. 
> 
> From that date, the Telerik and Kendo UI AI Coding Assistants will be available exclusively through our [MCP server]({%slug ai-mcp-server%}), ensuring you continue to enjoy the same powerful capabilities that are delivered by a modern, open, and officially recommended standard.


This extension enhances GitHub Copilot with proprietary context about Telerik MAUI controls, helping you:

* Generate code snippets using Telerik MAUI components.
* Get contextual suggestions for component properties and methods.
* Access best practices and implementation patterns.
* Speed up development with AI-powered code completion.

## Prerequisites

Before using the Telerik MAUI GitHub Copilot extension, ensure you have:

* An active [GitHub Copilot](https://github.com/features/copilot) subscription. You can enable or configure GitHub Copilot on the [Copilot Settings page in your GitHub account](https://github.com/settings/copilot).
@[template](/_contentTemplates/common/ai-coding-assistant.md#getting-started)
* The latest version of your [Copilot-enabled app](https://docs.github.com/en/copilot/building-copilot-extensions/about-building-copilot-extensions#supported-clients-and-ides) (for example, Visual Studio or Visual Studio Code).

## Installation

Follow these steps to install and configure the Telerik MAUI Copilot extension:

1. Go to the [Telerik MAUI GitHub App](https://github.com/apps/telerikmaui) page and click the **Install** button.
1. You will see a list that includes your GitHub account and all GitHub organizations that you are part of. Select your GitHub account.
1. Click the **Install & Allow** button. This will allow the GitHub Copilot extension to integrate with your GitHub account.
1. Enter your GitHub password when prompted.
1. You will be redirected to telerik.com. Enter your Telerik account credentials if prompted. This step links the GitHub Copilot extension with your Telerik account.
1. Upon successful Telerik authentication, you will be redirected to a confirmation page that indicates successful Copilot extension installation.
1. Restart your [Copilot-enabled app](https://docs.github.com/en/copilot/building-copilot-extensions/about-building-copilot-extensions#supported-clients-and-ides) (for example, Visual Studio and Visual Studio Code).
1. Start a new chat session in Copilot.

## Usage

To use the Telerik MAUI Copilot extension:

1. Open the GitHub Copilot chat window in your [Copilot-enabled app](https://docs.github.com/en/copilot/building-copilot-extensions/about-building-copilot-extensions#supported-clients-and-ides) (for example, Visual Studio or VS Code).
1. Ensure you are in **Chat** mode and not in **Edit** or **Agent** mode. The Edit and Agent modes do not use the Telerik Copilot extension. However, the Agent mode can use the [Telerik MAUI MCP server]({%slug ai-mcp-server%}).
1. Start your prompt with `@telerikmaui` and type your request. Verify that `@telerikmaui` is recognized and highlighted; otherwise, the extension may not be properly installed.
1. Look for a status label such as **Telerik MAUI working...** or **Telerik MAUI generating response...** in the output to confirm the extension is active.
1. Grant permission to the Telerik MAUI extension to read your workspace files when prompted.
1. For unrelated queries, start a new chat session in a new window to avoid context pollution from previous conversations.

### Sample Prompts

The following examples demonstrate useful prompts for the Telerik MAUI extension:

* "`@telerikmaui` Generate a DataGrid with 5 columns and 500 records. Enable sorting for the first column and include paging."
* "`@telerikmaui` Create a Telerik ComboBox with sample data for customers. Enable multiple selection and preselect the first two customers."
* "`@telerikmaui` Show me how to implement a Chart with line series."
* "`@telerikmaui` Generate a CollectionView with grouping and filtering capabilities."

## Number of Requests

@[template](/_contentTemplates/common/ai-coding-assistant.md#number-of-requests)

## Troubleshooting

If you encounter issues:

* Ensure the `@telerikmaui` mention is properly highlighted in your prompt.
* Verify that you have an active GitHub Copilot subscription.
* Restart your IDE after installation.
* Check that you're in Chat mode, not Edit or Agent mode.

## See Also 

* [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
* [GitHub Copilot Tutorials](https://github.com/features/copilot/tutorials)
* [Telerik MAUI MCP Server]({%slug ai-mcp-server%})
* [Telerik UI for .NET MAUI Documentation](https://docs.telerik.com/devtools/maui/)