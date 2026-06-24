---
title: Getting Started
meta_title: Get Started with the Telerik UI for .NET MAUI MCP Server
description: Learn how to install, configure, license, and use the Telerik UI for .NET MAUI MCP Server in Visual Studio, Visual Studio Code, and Cursor.
slug: ai-mcp-server
tags: telerik,maui,ai,ai server,dotnetmaui,coding assistant
position: 1
tag: updated
---

# Getting Started with the Telerik UI for .NET MAUI MCP Server

Use the Telerik UI for .NET MAUI [MCP (Model Context Protocol) server](https://modelcontextprotocol.io/introduction) to give compatible AI tools grounded context about Telerik UI for .NET MAUI components and APIs. This article shows how to install the server, configure `mcp.json`, add your Telerik license, verify that the server is running, and start using it in prompts.

The MCP server helps AI-powered IDEs and tools generate more accurate code, answer component questions with Telerik-specific context, and suggest implementations that match [Telerik UI for .NET MAUI components](https://www.telerik.com/maui-ui).

>tip
> The Telerik UI for .NET MAUI MCP server works in **Chat** (**Ask**) and **Agent** modes.

## What Can the MCP Server Help You Do

After you configure the server, you can use it to:

- Ask questions about Telerik UI for .NET MAUI components and APIs.
- Generate Telerik-specific control setup code, view models, and sample data.
- Get implementation guidance that is more accurate than generic AI output.
- Use the same Telerik-aware context across supported MCP clients.

## Prerequisites

To use the Telerik MAUI MCP server, you need:

* [.NET](https://learn.microsoft.com/en-us/dotnet/core/whats-new/dotnet-8/overview) 9 or later, or [Node.js](https://nodejs.org/en) 18 or later.
* An [MCP-compatible client](https://modelcontextprotocol.io/clients) that supports MCP tools (latest version recommended).

@[template](/_contentTemplates/common/ai-coding-assistant.md#getting-started)

## Quick Setup Checklist

Use this sequence for the fastest successful setup:

1. Choose whether you want to run the server with `.NET 10`, `.NET 9`, or `Node.js`.
2. Install the Telerik UI for .NET MAUI MCP server with the matching command.
3. Add the correct server entry to your `mcp.json` file.
4. Configure your Telerik license if it is not already available in the default location.
5. Restart your MCP client and verify that the `telerik-maui-assistant` server starts when prompted.

## Install the Telerik UI for .NET MAUI MCP Server

Choose the runtime that best matches your development environment:

| Runtime | Use It When | Install Command |
|---|---|---|
| .NET 10 or later | You want the simplest .NET-based setup without preinstalling a local tool. | `dnx Telerik.MAUI.MCP` |
| .NET 9 | You want to run the server through a locally installed .NET tool. | `dotnet tool install Telerik.MAUI.MCP` |
| Node.js 18 or later | You prefer a Node.js-based setup or need it for your editor workflow. | `npm install @progress/telerik-maui-mcp` |

Install the server package by using one of the following options:

- By using the `dnx` script or the `dotnet` CLI:

  ```bash .NET 10
  dnx Telerik.MAUI.MCP
  ```

  ```bash .NET 9
  dotnet tool install Telerik.MAUI.MCP
  ```

- By using npm:

  ```bash
  npm i @progress/telerik-maui-mcp
  ```

After the package is available, configure `mcp.json`, add your Telerik license if needed, restart your MCP client, and then verify that the server is running.

### Configuring mcp.json

Use the following values in the [`mcp.json` file](https://code.visualstudio.com/docs/copilot/customization/mcp-servers) of your editor. The exact wrapper differs by client, but the `command`, `args`, and server name stay the same.

| Setting Name | .NET 10 Value | .NET 9 Value | Node.js Value |
|---------|---------------|-----------------------|---------------|
| Package Name | `"Telerik.MAUI.MCP"` | `"Telerik.MAUI.MCP"` | `"@progress/telerik-maui-mcp"` |
| Type | `"stdio"` | `"stdio"` | `"stdio"` |
| Command | `"dnx"` | `"dotnet"` | `"npx"` |
| Arguments | `"Telerik.MAUI.MCP", "--yes"` | `"tool", "run", "telerik-maui-assistant"` | `"-y"` |
| Server Name | `"telerik-maui-assistant"` | `"telerik-maui-assistant"` | `"telerik-maui-assistant"` |

### Configuring Your License

An active Telerik UI for .NET MAUI license is required to use the Telerik MAUI MCP server.

- When you use the .NET tooling (`dnx` or `dotnet tool install`) and the [license key file]({%slug set-up-your-license%}) is stored in the default location, the server loads it automatically. The default path is `%AppData%\Telerik\telerik-license.txt` on Windows and `~/.telerik/telerik-license.txt` on Linux.
- When you use the .NET tooling and the [license key file]({%slug set-up-your-license%}) is stored in a different location, add one of the following `env` settings to `mcp.json`.
- When you use Node.js, add one of the following `env` settings to `mcp.json`:

  - As a license file path (recommended):

    ```json
    "env": {
        "TELERIK_LICENSE_PATH": "THE_PATH_TO_YOUR_LICENSE_FILE"
    }
    ```

  - As a license key value:

    ```json
    "env": {
        "TELERIK_LICENSE": "YOUR_LICENSE_KEY_HERE"
    }
    ```

>note Use a license file path unless you need to share settings across systems. When your Telerik license changes, [update the license key]({%slug set-up-your-license%}#updating-your-license-key) before you restart the MCP client.

## MCP Clients Configuration

Use the following client-specific examples to create a working `mcp.json` file. The configuration values are the same across clients, but the config file location and top-level property name differ.

| Client | Config File | Top-Level Property |
|---|---|---|
| Visual Studio | `.mcp.json` | `servers` |
| Visual Studio Code | `.vscode/mcp.json` or user-level `mcp.json` | `servers` |
| Cursor | `.cursor/mcp.json` | `mcpServers` |

<TabStrip>
<TabStripTab title="Visual Studio">

>note Early Visual Studio 17.14 versions require the Copilot Chat window to stay open while the solution loads. For platform-specific details, see [Use MCP servers in Visual Studio](https://learn.microsoft.com/en-us/visualstudio/ide/mcp-servers).

1. Add an `.mcp.json` file to either of the following locations:

    - For a workspace-specific setup, add the file to the solution folder.
    - For a global setup, add the file to your user directory, `%USERPROFILE%` (for example, `C:\Users\YourName\.mcp.json`).

    ```json .NET 10
    {
      "servers": {
        "telerik-maui-assistant": {
          "type": "stdio",
          "command": "dnx",
          "args": ["Telerik.MAUI.MCP", "--yes"]
        }
      }
    }
    ```

    ```json .NET 9
    {
      "servers": {
        "telerik-maui-assistant": {
          "type": "stdio",
          "command": "dotnet",
          "args": ["tool", "run", "telerik-maui-assistant"]
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

If you prefer to pass the license value directly, replace `TELERIK_LICENSE_PATH` with `TELERIK_LICENSE` in the `env` object.

</TabStripTab>
<TabStripTab title="Visual Studio Code">

>note Visual Studio Code `1.102.1` or later is required. For platform-specific details, see [Use MCP servers in Visual Studio Code](https://code.visualstudio.com/docs/copilot/chat/mcp-servers).

The basic setup in Visual Studio Code involves the following steps:

1. Enable [`chat.mcp.enabled`](vscode://settings/chat.mcp.enabled) in the Visual Studio Code settings.
2. Create a `.vscode/mcp.json` file in your workspace root (or user folder for global setup):

    ```json .NET 10
    {
      "servers": {
        "telerik-maui-assistant": {
          "type": "stdio",
          "command": "dnx",
          "args": ["Telerik.MAUI.MCP", "--yes"]
        }
      }
    }
    ```

    ```json .NET 9
    {
      "servers": {
        "telerik-maui-assistant": {
          "type": "stdio",
          "command": "dotnet",
          "args": ["tool", "run", "telerik-maui-assistant"]
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
            "TELERIK_LICENSE_PATH": "THE_PATH_TO_YOUR_LICENSE_FILE"
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

If you prefer to pass the license value directly, replace `TELERIK_LICENSE_PATH` with `TELERIK_LICENSE` in the `env` object.

</TabStripTab>
<TabStripTab title="Cursor">

>note For Cursor-specific details, see [Model Context Protocol in Cursor](https://docs.cursor.com/context/mcp).

Create a `.cursor/mcp.json` file in your workspace root (or user folder for global setup):

```json .NET 10
{
  "mcpServers": {
    "telerik-maui-assistant": {
      "type": "stdio",
      "command": "dnx",
      "args": ["Telerik.MAUI.MCP", "--yes"]
    }
  }
}
```

```json .NET 9
{
  "mcpServers": {
    "telerik-maui-assistant": {
      "type": "stdio",
      "command": "dotnet",
      "args": ["tool", "run", "telerik-maui-assistant"]
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

If you prefer to pass the license value directly, replace `TELERIK_LICENSE_PATH` with `TELERIK_LICENSE` in the `env` object.

</TabStripTab>
</TabStrip>

## Verify That the MCP Server Is Working

After you restart the client, confirm that the server is available before you begin a larger prompt:

1. Start a new chat or agent session.
2. Begin the prompt with one of the Telerik triggers.
3. Approve tool permissions when the client asks.
4. Confirm that the editor shows the Telerik MAUI MCP server as running.

Use one of the following trigger strings in your prompt:

- `#telerik`
- `#telerikmaui`
- `#telerik-maui-assistant`

Look for one of the following client messages:

- Visual Studio: `Running telerik-maui-assistant`
- Visual Studio Code: `Running telerik-maui-assistant`
- Cursor: `Calling MCP tool telerik-maui-assistant`

## Troubleshooting

If the server does not appear or does not respond, check the following items first:

- Confirm that your installed runtime matches the configuration in `mcp.json`.
- Confirm that the JSON file is valid and uses the correct top-level property for your client.
- Confirm that your Telerik license file path or license value is available to the editor process.
- Restart the editor after every `mcp.json` change.

>warning
> **Known Issue: Hanging tool calls in Visual Studio**
>
> When you use Telerik AI tools in Visual Studio, GitHub Copilot may:
> - **hang** during tool invocation;
> - show UI for a successful tool response, but actually **fail silently**;
> - continue generation without waiting for **parallel tool calls**.
>
> In these cases, the response may be generated but not shown in the Copilot Agent UI.
>
> This is a known issue in Visual Studio Copilot, not in Telerik MCP servers or Telerik AI tools, and it does not reproduce in Visual Studio Code.
>
> For more details, see the [Visual Studio Developer Community issue for hanging Copilot tool calls](https://developercommunity.visualstudio.com/t/Copilot-stopped-working-after-latest-upd/10936456).
>
> Microsoft has marked the issue as **Fixed - Pending Release**. A future Visual Studio update is expected to resolve it.

## Usage

MCP clients do not always call tools deterministically. When your client supports explicit tool selection, reference the Telerik server directly in the prompt to increase the chance that the client uses Telerik-specific context.

Use the following practices when you work with the Telerik MAUI MCP server:

1. Start the prompt with `#telerik`, `#telerikmaui`, or `#telerik-maui-assistant`.
2. Keep the request specific by naming the Telerik control, layout, data source, or behavior you want.
3. Grant permissions when the client prompts you.
4. Start a fresh session for unrelated prompts so earlier context does not affect the next result.
5. Use the server in **Chat** (**Ask**) and **Agent** modes.

### Increase Tool Selection Reliability

To increase the likelihood that your AI client uses the Telerik server, add client-specific instructions that mention Telerik UI for .NET MAUI as a preferred source for component generation and API guidance:

- [GitHub Copilot custom instructions](https://docs.github.com/en/copilot/customizing-copilot/adding-repository-custom-instructions-for-github-copilot#about-repository-custom-instructions-for-github-copilot-chat)
- [Cursor rules](https://docs.cursor.com/context/rules)

### Sample Prompts

Use prompts like the following examples when you want the client to generate Telerik-specific code:

* "`#telerik-maui-assistant Create new maui project with Telerik. Add sample usage of the DataGrid component.`"
* "`#telerik-maui-assistant Create a DataGrid with 3 columns - Name, Country, City. Add the corresponding business object in the code behind and populate it with sample data. Add 20 entries to the data.`"
* "`#telerik-maui-assistant Add CollectionView. Enable drag and drop operation in the control.`"

## Number of Requests

@[template](/_contentTemplates/common/ai-coding-assistant.md#number-of-requests)

## Local AI Model Integration

You can use the Telerik MAUI MCP server with a local large language model (LLM) instead of a cloud-hosted model:

1. Run a local model, for example, [Ollama](https://ollama.com).
2. Use a bridge package like [MCP-LLM Bridge](https://github.com/patruff/ollama-mcp-bridge).
3. Connect the local model and the Telerik MAUI MCP server through the bridge.

This setup allows you to use the Telerik AI Coding Assistant without a cloud-based AI model.

## See Also

- [AI Coding Assistant Overview]({%slug ai-overview%})
- [Set Up Your Telerik License]({%slug set-up-your-license%})
