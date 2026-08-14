---
title: First Steps
page_title: First Steps with Telerik UI for .NET MAUI
description: "Get started with Telerik UI for .NET MAUI. Set up your license, install the Telerik package, register the controls, and add a component."
tags: maui, dotnet maui, microsoft maui, telerik maui, nuget, ui for .net maui, macos, install, quick
slug: maui-quick-start
tag: updated
previous_url: /maui-getting-started, /get-started/first-steps, /installation/windows/install-msi, /first-steps, /get-started/windows/first-steps-msi, /get-started/windows/first-steps-nuget, /installation/mac/install-pkg, /get-started/mac/first-steps-nuget, /get-started/mac/first-steps-pkg
position: 1
---

# First Steps with Telerik UI for .NET MAUI

This guide walks you through the essential steps to get Telerik UI for .NET MAUI up and running in your app.

## Prerequisites

The following table lists the requirements to build .NET MAUI apps with Telerik UI for .NET MAUI:

| Requirement | Minimum version |
|---|---|
| [.NET SDK](https://dotnet.microsoft.com/en-us/download) | 9.0 or later |
| Operating system | Windows or macOS |
| Telerik account | Active subscription or trial license required. |
| IDE | Visual Studio 2022 17.12 or later, or Visual Studio Code with the .NET MAUI workloads installed. |

> Telerik UI for .NET MAUI supports .NET 11.0 Preview 6 (starting with version 15.0.0).

## Set Up Telerik Development Environment

This getting started guide uses the Telerik CLI .NET command tool to set up your development environment. The Telerik CLI is a command-line interface that helps you manage your Telerik account, license, NuGet package sources and Telerik MCP server.

1. Install the Telerik CLI:

```powershell
dotnet tool install -g Telerik.CLI --source https://api.nuget.org/v3/index.json
```

2. Run the Telerik.CLI `setup` command:

```powershell
telerik setup maui
```

The `telerik setup maui` command performs multiple actions to configure your Telerik development environment:

&#10003; Creates your Telerik account or log in if you already have one.

&#10003; Activates a Telerik UI for MAUI trial if you don't have an active license.

&#10003; Downloads your Telerik license key file and saves `telerik-license.txt` to your operating system user's folder, making it available to all Telerik .NET apps on your machine.

&#10003; Configures the Telerik NuGet package source.

&#10003; Installs the Telerik MCP server for AI-powered coding assistance.

&#10003; Installs the Telerik UI for MAUI project templates.

## Create New MAUI Project

This section assumes that you have successfully installed the Telerik UI for MAUI project templates in the [previous step](#set-up-telerik-development-environment).

To create a new Telerik .NET MAUI app, use your preferred approach:

<TabStrip>
<TabStripTab title="Telerik.CLI">

Run the following Telerik.CLI command to create a new Telerik .NET MAUI app interactively:

```powershell
telerik create maui
```

Follow the instructions for creating a .NET MAUI app. The command creates a new project using the Telerik MAUI ProjectTemplates&mdash;**Telerik .NET MAUI Blank App** or **Telerik .NET MAUI Blank Shell App**.

When the project is ready, navigate to the project folder and open the app in your preferred IDE.

</TabStripTab>
<TabStripTab title=".NET CLI">

Use the .NET CLI `dotnet new` command to create a new Telerik .NET MAUI Blank App:

```powershell
dotnet new telerik-maui -o MyNewTelerikMAUIAppName
```

> If the above command fails with type of error: `No templates or subcommands found matching:` , run the following command in the terminal first:
> ```powershell
> dotnet new install Telerik.Maui.Templates
> ```
> Then run the command: `dotnet new telerik-maui -o MyNewTelerikMAUIAppName`

The application includes the Telerik UI for .NET MAUI suite already set up. 

When the project is ready, navigate to the project folder and open the app in your preferred IDE.

For more detials about the Telerik UI for .NET MAUI projectTemplates in .NET CLI, review the [Telerik.Maui.Templates packages](https://www.nuget.org/packages/Telerik.Maui.Templates).

</TabStripTab>
</TabStrip>

## Next Steps

@[template](/_contentTemplates/common/see-also.md#see-also)

