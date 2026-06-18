#telerik-cli
The Telerik CLI is a .NET global tool that automates common Telerik development tasks from the command line. Use the Telerik CLI to configure the Telerik NuGet package source, create new projects from Telerik templates, and update Telerik UI for MAUI packages without opening IDE.

## Prerequisites

The following table lists the requirements to run the Telerik CLI for using Telerik UI for .NET MAUI:

| Requirement | Minimum version | Notes |
|---|---|---|
| .NET SDK | 9.0 or 10.0 | Required to install and run .NET global tools and building .NET MAUI apps. |
| Operating system | Windows or macOS | OS supported by the .NET SDK. |
| Telerik account | N/A | Active Subscription or Trial license required. |

## Command Reference

The following table lists all Telerik CLI commands with their purpose and usage.

| Command | Description | Usage |
|---|---|---|
| `dotnet tool install -g Telerik.CLI` | Installs the Telerik CLI as a .NET global tool. | Run once to install the CLI on your machine. |
| `dotnet tool update -g Telerik.CLI` | Updates the Telerik CLI to the latest version. | Run periodically to get the latest features and fixes. |
| `telerik nuget` | Configures the Telerik NuGet server to your package sources. | Run to set up the `https://nuget.telerik.com/v3/index.json` feed in your NuGet configuration. |
| `telerik license get-key` | Downloads your Telerik license key and saves it as `telerik-license.txt`. | Run to download your license key file. |
| `telerik mcp config` | Installs and configures the Telerik MCP Server for your IDE. | Run to set up AI coding assistance in Visual Studio, VS Code, or Cursor. |
| `telerik login` | Authenticates with your Telerik account. Use `--no-browser` for manual authentication. | Run to store credentials for subsequent commands. |
| `telerik whoami` | Displays the currently logged-in Telerik user account email. | Run to verify your authentication state. |
| `telerik logout` | Logs out from the Telerik CLI. | Run to log out the credentials from your Telerik account. |

## Install the Telerik CLI

The [Telerik CLI NuGet](https://www.nuget.org/packages/Telerik.CLI) package is hosted on `nuget.org`. Run the following commands in your preferred command shell:

Install the Telerik CLI .NET tool globally on your machine:

```powershell
dotnet tool install -g Telerik.CLI --source https://api.nuget.org/v3/index.json
```

The `--source` option is not required, but it avoids issues if any of the installed NuGet sources is misconfigured.

The `dotnet tool install` command provides a few ways for you to install .NET tools on your machine.
* To install the Telerik CLI globally, use the `-g` option.
* To install the Telerik CLI in a custom location, use the `--tool-path` option.
* To install the Telerik CLI in the current folder only, omit the `-g` and `--tool-path` options.


To verify the installation:

```powershell
dotnet tool list -g
```

To update to the latest version:

```powershell
dotnet tool update -g Telerik.CLI
```

## Automatic Set Up Telerik Environment

To open the Telerik.CLI command-line panel run the `telerik` command.

1. Select the `Set up your environment` option and press `Enter` key.

2. Select `Telerik UI for .NET MAUI` and press `Enter` key.

3. Follow the instructions for login, downloading license key, setting up the Telerik NuGet server and installing the mcp server.

If you do not want to use the Telerik.CLI panel, you can run the following command in the terminal to start setting up the Telerik .NET MAUI:

```powershell
telerik setup maui
```

The `telerik setup` command performs the following multiple actions at once to configure your Telerik development environment:

* [Login](#log-in-to-your-telerik-account)
* [Download license key](#get-license-key)
* [Configure NuGet package source](#set-up-telerik-nuget-feed)
* [Install MCP server(s)](#install-mcp-server)

## Manual Set Up Telerik Environment

If you do not want to use Telerik.CLI panel, you can run the commands described in the next sections to set up the Telerik .NET MAUI environment manually.

## Log In to Your Telerik Account

Most Telerik CLI commands are related to your Telerik identity. It's recommended to log in first, so that all the other commands work without the need for additional authentication.

To log in to your Telerik account automatically:

```powershell
telerik login
```

The `login` command opens `https://identity.telerik.com` in a browser window where you need to provide your Telerik account credentials. The browser performs a few redirects to complete the log in.

If this browser integration fails due to security or network restrictions, you can authenticate manually by using the `--no-browser` option.

### Using `--no-browser` (Manual Authentication)

If automatic browser-based authentication is blocked (for example, by corporate network policies, restricted browsers, or headless CI environments), use the `--no-browser` switch to perform a manual login flow:

```powershell
telerik login --no-browser
```
When you run `telerik login --no-browser` the CLI will:

1. Prints a short URL and a one-time code in the terminal.
2. Instructs you to open the URL on any device or browser with network access (for example, your desktop browser or a browser on another machine).
3. Asks you to enter the one-time code and sign in to your Telerik account in the browser.

After successful authentication the browser will display a success message and you can return to the CLI — it will detect the completed sign-in and store the session token locally.

The Telerik CLI stores a session token in:

| Operating System | Path |
| --- | --- |
| Windows | `%AppData%\Telerik` |
| macOS | `~/.telerik` |

The session token is valid for one month.

### Check Login State

To see which Telerik user is logged in the CLI, use the `whoami` command:

```powershell
telerik whoami
```

The CLI will output your Telerik user account email.

## Log Out from Your Telerik Account

To log out from the Telerik CLI, use the `logout` command.

```powershell
telerik logout
```

## Get License Key

To download or update your [Telerik license key]({%slug license-key%}), use the `license get-key` command:

```powershell
telerik license get-key
```

The `license get-key` command downloads your up-to-date Telerik license key and creates a `telerik-license.txt` file in your operating system user's folder.

## Set Up Telerik NuGet Feed

To add the Telerik NuGet server to your package sources, use the `nuget config` command:

```powershell
telerik nuget config
```

By default, the `nuget config` command updates your [global `NuGet.Config` file](https://learn.microsoft.com/en-us/nuget/consume-packages/configuring-nuget-behavior). The newly added Telerik NuGet feed name is `TelerikNuGetV3`. The command generates a new API key that you can delete and revoke from the [API Keys page in your Telerik account](https://www.telerik.com/account/downloads/api-keys).

> Telerik NuGet API keys expire in two years.

You can use the `nuget config` command with the following options:

* `--scope project` and `--path` that points to the folder that contains the `NuGet.Config` file to modify. The default `--scope` value is `user`.
* `--api-key` to provide an existing Telerik NuGet API key inline, otherwise the CLI generates a new one.
* `--force` to overwrite any existing Telerik credentials in the `NuGet.Config` file.

```powershell
telerik nuget config --scope project --path . --force
```

## Install MCP Server

To install the Telerik MCP servers, use the `mcp config` command:

```powershell
telerik mcp config
```

By default, the command creates or updates the global `.mcp.json` configuration files for all supported IDEs and registers all currently available Telerik MCP servers for Telerik products.

| IDE | Operating System | Configuration File Path |
| --- | --- | --- |
| Visual Studio | Windows | `%USERPROFILE%\.mcp.json` |
| VS Code | Windows | `%APPDATA%\Code\User\mcp.json`  |
| VS Code | macOS | `~/Library/Application Support/Code/User/mcp.json` |
| Cursor  | Windows | `%USERPROFILE%\.cursor\mcp.json` |
| Cursor | macOS | `~/.cursor/mcp.json` |

### Install MAUI MCP Server

You can also fine-tune the process with the following options:

* Specify which Telerik products you are interested in, for example, just `maui`.
* `--ide` specifies your preferred IDE. The supported values are `visualstudio`, `vscode`, `cursor`, and `all`.

<TabStrip>
<TabStripTab title="Visual Studio">

Run the following command to install the MAUI MCP server for Visual Studio:

```powershell
telerik mcp config maui --ide visualstudio
```

Use `--json` to return machine-readable output:

```powershell
telerik mcp config maui --ide visualstudio --json
```

Example output:

```json
{
  "exitCode": 0,
  "message": "MCP servers registered successfully.",
  "data": {
    "registeredIdes": [
      "Visual Studio"
    ],
    "registered": [
      {
        "ide": "Visual Studio",
        "configPath": "C:\\Users\\username\\.mcp.json"
      }
    ]
  },
  "success": true
}
```

</TabStripTab>
<TabStripTab title="Visual Studio Code">

Run the following command to install the MAUI MCP server for Visual Studio Code:

```powershell
telerik mcp config maui --ide vscode
```

Use `--json` to return machine-readable output:

```powershell
telerik mcp config maui --ide vscode --json
```

Example output:

```json
{
  "exitCode": 0,
  "message": "MCP servers registered successfully.",
  "data": {
    "registeredIdes": [
      "Visual Studio Code"
    ],
    "registered": [
      {
        "ide": "Visual Studio Code",
        "configPath": "C:\\Users\\username\\AppData\\Roaming\\Code\\User\\mcp.json"
      }
    ]
  },
  "success": true
}
```

</TabStripTab>
</TabStrip>

## Help

To get help about the tool or a specific command in the Telerik CLI, use the `-h` option:

```powershell
telerik -h 

telerik nuget -h

telerik nuget config -h
```

## Uninstall Telerik CLI

To uninstall the Telerik CLI:

```powershell
dotnet tool uninstall -g Telerik.CLI
```
#end