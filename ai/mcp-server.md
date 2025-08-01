---
title: MCP Server
page_title: Telerik MAUI MCP Server
description: Learn how to add and use the Telerik MAUI MCP Server as a .NET MAUI AI coding assistant and code generator for better developer productivity. The Telerik MAUI MCP server provides proprietary context about Telerik UI for .NET MAUI to AI-powered software.
slug: ai-mcp-server
tags: telerik,maui,ai,ai server,dotnetmaui,coding assistant
position: 20
---

# Telerik .NET MAUI MCP Server

The Telerik MAUI [MCP (Model Context Protocol) Server](https://modelcontextprotocol.io/introduction) enhances your AI-powered development experience by providing specialized context about Telerik UI for .NET MAUI components.

This MCP server enables AI-powered IDEs and tools to generate more accurate, tailored code that leverages [Telerik UI for .NET MAUI components](https://www.telerik.com/maui-ui) and APIs. You can ask complex questions about Telerik components, request specific implementations, and generate comprehensive code solutions.

## Prerequisites

To use the Telerik MAUI MCP server, you need:

* [Node.js](https://nodejs.org/en) 18 or newer.
* An [MCP-compatible client](https://modelcontextprotocol.io/clients) that supports **MCP tools** (latest version recommended).

@[template](/_contentTemplates/common/ai-coding-assistant.md#getting-started)

## Installation

Install the Telerik MAUI MCP server using npm:

```bash
npm i @progress/telerik-maui-mcp
```

### Configuration

Use these settings when configuring the server in your MCP client:

| Setting | Value |
|---------|-------|
| Package Name | `@progress/telerik-maui-mcp` |
| Type | `stdio` (standard input/output transport) |
| Command | `npx` |
| Arguments | `-y` |
| Server Name | `telerikMauiAssistant` (customizable) |

### License Configuration

Add your [Telerik license key]({%slug set-up-your-license%}) as an environment parameter in your `mcp.json` file using one of these options:

Option 1: License File Path (Recommended)

 ```json
 "env": {
     "TELERIK_LICENSE_PATH": "THE_PATH_TO_YOUR_LICENSE_FILE"
 }
 ```

Option 2: Direct License Key

 ```json
 "env": {
     "TELERIK_LICENSE": "YOUR_LICENSE_KEY_HERE"
 }
 ```

> Option 1 is recommended unless you're sharing settings across different systems. Remember to [update your license key]({%slug set-up-your-license%}#updating-your-license-key) when necessary.

## Visual Studio

For complete setup instructions, see [Use MCP servers in Visual Studio](https://learn.microsoft.com/en-us/visualstudio/ide/mcp-servers).

> Early Visual Studio 17.14 versions require the Copilot Chat window to be open when opening a solution for the MCP server to work properly.

### Workspace-Specific Setup:

1. Add `.mcp.json` to your solution folder:

 ```json
 {
   "servers": {
     "telerikMauiAssistant": {
       "type": "stdio",
       "command": "npx",
       "args": ["-y", "@progress/telerik-maui-mcp@latest"],
       "env": {
         "TELERIK_LICENSE_PATH": "THE_PATH_TO_YOUR_LICENSE_FILE",
         // or
         "TELERIK_LICENSE": "YOUR_LICENSE_KEY"
       }
     }
   }
 }
 ```

2. Restart Visual Studio.
3. Enable the `telerikMauiAssistant` tool in the [Copilot Chat window's tool selection dropdown](https://learn.microsoft.com/en-us/visualstudio/ide/mcp-servers?view=vs-2022#configuration-example-with-github-mcp-server).

### Global Setup:

Add the `.mcp.json` file to your user directory (`%USERPROFILE%`, e.g., `C:\Users\YourName\.mcp.json`).

## Visual Studio Code

For complete setup instructions, see [Use MCP servers in Visual Studio Code](https://code.visualstudio.com/docs/copilot/chat/mcp-servers).

> Visual Studio Code 1.102.1 or newer is required to use the Telerik MCP Server

The basic setup in Visual Studio Code follows these steps:

1. Enable [`chat.mcp.enabled`](vscode://settings/chat.mcp.enabled) in Visual Studio Code settings.
2. Create `.vscode/mcp.json` in your workspace root (or user folder for global setup):

 ```json
 {
   "servers": {
     "telerik-maui-assistant": {
       "type": "stdio",
       "command": "npx",
       "args": ["-y", "@progress/telerik-maui-mcp@latest"],
       "env": {
         "TELERIK_LICENSE_PATH": "THE_PATH_TO_YOUR_LICENSE_FILE",
         // or
         "TELERIK_LICENSE": "YOUR_LICENSE_KEY"
       }
     }
   }
 }
 ```

3. For global discovery, enable [`chat.mcp.discovery.enabled`](vscode://settings/chat.mcp.discovery.enabled) in `settings.json`:

 ```json
 {
   "chat.mcp.discovery.enabled": true
 }
 ```

4. Restart Visual Studio Code.

## Cursor

For complete setup instructions, see [Model Context Protocol](https://docs.cursor.com/context/mcp).

Create `.cursor/mcp.json` in your workspace root (or user folder for global setup):

```json
{
  "mcpServers": {
    "telerikMauiAssistant": {
      "type": "stdio",
      "command": "npx",
      "args": ["-y", "@progress/telerik-maui-mcp@latest"],
      "env": {
        "TELERIK_LICENSE_PATH": "THE_PATH_TO_YOUR_LICENSE_FILE",
        // or
        "TELERIK_LICENSE": "YOUR_LICENSE_KEY"
      }
    }
  }
}
```

## Usage

To use the Telerik MCP Server:

1. Start your prompt with one of these triggers:
   - `/telerik` / `@telerik` / `#telerik`
   - `/telerikmaui` / `@telerikmaui` / `#telerikmaui`
   - `#telerik-maui-assistant`

2. Verify server activation by looking for these messages:
   - Visual Studio: `Running telerikMauiAssistant`
   - Visual Studio Code: `Running telerik-maui-assistant`
   - Cursor: `Calling MCP tool telerikMauiAssistant`

3. Grant permissions when prompted (per session, workspace, or always).

4. Start fresh sessions for unrelated prompts to avoid context pollution.

### Improving Server Usage

To increase the likelihood of the Telerik MCP server being used, add custom instructions to your AI tool:
- [GitHub Copilot custom instructions](https://docs.github.com/en/copilot/customizing-copilot/adding-repository-custom-instructions-for-github-copilot#about-repository-custom-instructions-for-github-copilot-chat)
- [Cursor rules](https://docs.cursor.com/context/rules)

### Sample Prompts

The following examples demonstrate useful prompts for the Telerik .NET MAUI MCP Server:

* "`/telerik` Generate a DataGrid with sorting and paging. Bind it to a Person model with sample ViewModel."
* "`/telerikmaui` Create a ComboBox showing a product list. Include Product class and sample data."
* "`/telerik` Build a CollectionView with sorting and filtering capabilities."

## Number of Requests

@[template](/_contentTemplates/common/ai-coding-assistant.md#number-of-requests)

## Local AI Model Integration

You can use the Telerik MAUI MCP server with local large language models (LLMs):

1. Run a local model, for example, through [Ollama](https://ollama.com).
2. Use a bridge package like [MCP-LLM Bridge](https://github.com/patruff/ollama-mcp-bridge).
3. Connect your local model to the Telerik MCP server.

This setup allows you to use the Telerik AI Coding Assistant without cloud-based AI models.

## See Also

* [Telerik MAUI GitHub Copilot Extension]({%slug ai-copilot-extension%})
* [AI Coding Assistant Overview]({%slug ai-overview%})
