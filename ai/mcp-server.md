---
title: MCP Server
page_title: Telerik MAUI MCP Server
description: Learn how to add and use the Telerik MAUI MCP Server as a .NET MAUI AI coding assistant and code generator for better developer productivity. The Telerik MAUI MCP server provides proprietary context about Telerik UI for .NET MAUI to AI-powered software.
slug: ai-mcp-server
tags: telerik,maui,ai,ai server,dotnetmaui,coding assistant
position: 1
---

# Telerik UI for .NET MAUI MCP Server

The Telerik MAUI [MCP (Model Context Protocol) server](https://modelcontextprotocol.io/introduction) enhances your AI-powered development experience by providing specialized context about Telerik UI for .NET MAUI components.

This MCP server enables AI-powered IDEs and tools to generate more accurate, tailored code that leverages [Telerik UI for .NET MAUI components](https://www.telerik.com/maui-ui) and APIs. You can ask complex questions about Telerik components, request specific implementations, and generate comprehensive code solutions.

>tip The Telerik MAUI MCP server works in **Chat** (**Ask**) and **Agent** modes.


## Prerequisites

To use the Telerik MAUI MCP server, you need:

* [.NET](https://learn.microsoft.com/en-us/dotnet/core/whats-new/dotnet-8/overview) 8 or later, or [Node.js](https://nodejs.org/en) 18 or later.
* An [MCP-compatible client](https://modelcontextprotocol.io/clients) that supports MCP tools (latest version recommended).

@[template](/_contentTemplates/common/ai-coding-assistant.md#getting-started)

## Installation

Depending on your environment, you can install the Telerik MAUI MCP server in any of the following ways:

* By using the `dnx` script (.NET 10 or later only) or the `dotnet` CLI (.NET 8 and .NET 9):

  ```bash .NET 10
  dnx Telerik.MAUI.MCP
  ```
  ```bash .NET 8/9
  dotnet tool install Telerik.MAUI.MCP
  ```

* By using npm:

  ```bash
  npm i @progress/telerik-maui-mcp
  ```

Next, make sure the configuration in your `mcp.json` is [correct](#configuring-mcp-json), and then [add your Telerik license](#configuring-your-license).

### Configuring mcp.json

Use the settings in the following table to configure the Telerik MAUI MCP server in the [`mcp.json` file](https://code.visualstudio.com/docs/copilot/customization/mcp-servers) of your code editor. Select the correct value based on your development environment.

| Setting Name | .NET 10 Value | .NET 8 / .NET 9 Value | Node.js Value |
|---------|---------------|-----------------------|---------------|
| Package Name | `"Telerik.MAUI.MCP"` | `"Telerik.MAUI.MCP"` | `"@progress/telerik-maui-mcp"` |
| Type | `"stdio"` | `"stdio"` | `"stdio"` |
| Command | `"dnx"` | `"dotnet"` | `"npx"` |
| Arguments | `"Telerik.MAUI.MCP", "--yes"` | `"tool", "run", "telerik-maui-assistant"` | `"-y"` |
| Server Name | `"telerik-maui-assistant"` | `"telerik-maui-assistant"` | `"telerik-maui-assistant"` |

### Configuring Your License

An active Telerik UI for .NET MAUI license is required to use the Telerik MAUI MCP server.

* When installing the MCP server by using the .NET tooling (`dnx` or `dotnet tool install`), the [license key file]({%slug set-up-your-license%}) will be retrieved automatically if it is present in the default directory on your system (`%AppData%\Telerik\telerik-license.txt` on Windows and `~/.telerik/telerik-license.txt` on Linux.). No additional action is required.
* When using the .NET tooling, but your [license key file]({%slug set-up-your-license%}) is not in the default directory, use one of the options below.
* When using Node.js, add your [license key file]({%slug set-up-your-license%}) as an environment variable in your `mcp.json` file using one of the options below:

  * As a license file path (recommended)

    ```json
    "env": {
        "TELERIK_LICENSE_PATH": "THE_PATH_TO_YOUR_LICENSE_FILE"
    }
    ```

  * As a license key value

    ```json
    "env": {
        "TELERIK_LICENSE": "YOUR_LICENSE_KEY_HERE"
    }
    ```

> Using a license file path is recommended unless you're sharing settings across different systems. Remember to [update your license key]({%slug set-up-your-license%}#updating-your-license-key) when necessary.

## Visual Studio

> * Early Visual Studio 17.14 versions require the Copilot Chat window to be open when a solution loads for the MCP server to work properly.
> * For complete setup instructions, see [Use MCP servers in Visual Studio](https://learn.microsoft.com/en-us/visualstudio/ide/mcp-servers).

1. Add an `.mcp.json` file to either of the following locations:

    * For a workspace-specific setup, add the file to the solution's folder.
    * For a global setup, add the file to your user directory, `%USERPROFILE%` (for example, `C:\Users\YourName\.mcp.json`).

    ```json .NET 10
    {
      "servers": {
        "telerik-maui-assistant": {
          "type": "stdio",
          "command": "dnx",
          "args": ["Telerik.MAUI.MCP", "--yes"],
        }
      }
    }
    ```
    ```json .NET 8/9
    {
      "servers": {
        "telerik-maui-assistant": {
          "type": "stdio",
          "command": "dotnet",
          "args": ["tool", "run", "telerik-maui-assistant"],
        }
      }
    }
    ```
    ```json Node.js
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

2. Restart Visual Studio.
3. Enable the Telerik MAUI MCP server in the [Copilot Chat window's tool selection dropdown](https://learn.microsoft.com/en-us/visualstudio/ide/mcp-servers?view=vs-2022#configuration-example-with-github-mcp-server).

## Visual Studio Code

> * Visual Studio Code 1.102.1 or later is required to use the Telerik MAUI MCP Server.
> * For complete setup instructions, see [Use MCP servers in Visual Studio Code](https://code.visualstudio.com/docs/copilot/chat/mcp-servers).

The basic setup in Visual Studio Code involves the following steps:

1. Enable [`chat.mcp.enabled`](vscode://settings/chat.mcp.enabled) in the Visual Studio Code settings.
2. Create a `.vscode/mcp.json` file in your workspace root (or user folder for global setup):

    ```json .NET 10
    {
      "servers": {
        "telerik-maui-assistant": {
          "type": "stdio",
          "command": "dnx",
          "args": ["Telerik.MAUI.MCP", "--yes"],
        }
      }
    }
    ```
    ```json .NET 8/9
    {
      "servers": {
        "telerik-maui-assistant": {
          "type": "stdio",
          "command": "dotnet",
          "args": ["tool", "run", "telerik-maui-assistant"],
        }
      }
    }
    ```
    ```json Node.js
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

> For complete setup instructions, see [Model Context Protocol](https://docs.cursor.com/context/mcp).

Create a `.cursor/mcp.json` file in your workspace root (or user folder for global setup):

```json .NET 10
{
  "mcpServers": {
    "telerik-maui-assistant": {
      "type": "stdio",
      "command": "dnx",
      "args": ["Telerik.MAUI.MCP", "--yes"],
    }
  }
}
```
```json .NET 8/9
{
  "mcpServers": {
    "telerik-maui-assistant": {
      "type": "stdio",
      "command": "dotnet",
      "args": ["tool", "run", "telerik-maui-assistant"],
    }
  }
}
```
```json Node.js
{
  "mcpServers": {
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

## Usage

By default, MCP clients do not call MCP tools in a deterministic way. Some MCP clients like VS Code allow you to explicitly reference the desired MCP tool in your prompt.

To use the Telerik MAUI MCP server:

1. Start your prompt with one of these triggers:
   - `#telerik`
   - `#telerikmaui`
   - `#telerik-maui-assistant`

2. Verify server activation by looking for these messages:
   - Visual Studio: `Running telerik-maui-assistant`
   - Visual Studio Code: `Running telerik-maui-assistant`
   - Cursor: `Calling MCP tool telerik-maui-assistant`

3. Grant permissions when prompted (per session, workspace, or always).

4. Start a fresh session for unrelated prompts to avoid context pollution.

5. Use in **Chat** (**Ask**) and **Agent** modes.

### Improving Server Usage

To increase the likelihood of the Telerik MAUI MCP server being used, add custom instructions to your AI tool:
- [GitHub Copilot custom instructions](https://docs.github.com/en/copilot/customizing-copilot/adding-repository-custom-instructions-for-github-copilot#about-repository-custom-instructions-for-github-copilot-chat)
- [Cursor rules](https://docs.cursor.com/context/rules)

### Sample Prompts

The following examples demonstrate useful prompts for the Telerik MAUI MCP server:

* "`#telerik-maui-assistant Create new maui project with Telerik. Add sample usage of the DataGrid component.`"
* "`#telerik-maui-assistant Create a DataGrid with 3 columns - Name, Country, City. Add the corresponding business object in the code behind and populate it with sample data. Add 20 entries to the data.`"
* "`#telerik-maui-assistant Add CollectionView. Enable drag and drop operation in the control.`"

## Number of Requests

@[template](/_contentTemplates/common/ai-coding-assistant.md#number-of-requests)

## Local AI Model Integration

You can use the Telerik MAUI MCP server with local large language models (LLMs):

1. Run a local model, for example, [Ollama](https://ollama.com).
2. Use a bridge package like [MCP-LLM Bridge](https://github.com/patruff/ollama-mcp-bridge).
3. Connect your local model to the Telerik MAUI MCP server.

This setup allows you to use the Telerik AI Coding Assistant without cloud-based AI models.

## See Also

* [Telerik MAUI GitHub Copilot Extension]({%slug ai-copilot-extension%})
* [AI Coding Assistant Overview]({%slug ai-overview%})
