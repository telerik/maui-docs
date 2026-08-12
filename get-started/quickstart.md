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

Run the following Telerik CLI command to create a new Telerik .NET MAUI app interactively:

```powershell
telerik create maui
```

Follow the instructions for creating a .NET MAUI app. The command creates a new project using the Telerik MAUI ProjectTemplates&mdash;**Telerik .NET MAUI Blank App** or **Telerik .NET MAUI Blank Shell App**.

When the project is ready, navigate to the project folder and open the app in your preferred IDE.

</TabStripTab>
<TabStripTab title=".NET CLI">

</TabStripTab>
<TabStripTab title="Visual Studio">

### Step 1: Create a New MAUI Project

1. Open Visual Studio and select **Create a new project** in the start window.

1. Select the **.NET MAUI App** template, and click the **Next** button.

1. Name your project and select a location.

1. Choose the .NET framework for your project.

1. Wait until Visual Studio restores all dependencies (when done, all exclamation marks in the **Dependencies** tree view item disappear).

1. Click the **Windows Machine** button to build and run the app.

If you encounter any issues creating the basic project, see the complete guide in <a href="https://learn.microsoft.com/en-us/dotnet/maui/get-started/first-app?pivots=devices-windows&view=net-maui-8.0&tabs=vswin" target="_blank">Microsoft's .NET MAUI documentation</a>.

### Step 2: Install the Telerik UI for .NET MAUI Controls

1. In Visual Studio go to **Tools** > **NuGet Package Manager** > **Manage NuGet Packages for Solution...**.

1. Make sure the **Package source** is set to `nuget.org`.

1. Select the **Browse** tab, enter `Telerik.UI.for.Maui` in the search box, and select the package.

1. Select the checkbox for the target project, and then click **Install**.

### Step 3: Add the Telerik Namespace and Register the Controls

@[template](/_contentTemplates/get-started.md#add-namespace-register-controls)

### Step 4: Add a Telerik UI Component

@[template](/_contentTemplates/get-started.md#add-telerik-component)

</TabStripTab>
<TabStripTab title="Visual Studio Code">

### Step 1: Create a New MAUI Project

1. Open Visual Studio Code and open the Command Palette by pressing `Cmd`+`Shift`+`P` on Mac or `Ctrl`+`Shift`+`P` on Windows.
1. Enter **.NET: New Project...** in the input field.

1. Select the **.NET MAUI App** option.

1. Enter a name for your app.

1. Select an empty folder for your project. If the folder is not empty, the file explorer opens again.

1. Wait for Visual Studio Code to create the project and complete its configuration.

If you encounter any issues creating the basic project, see the complete guide in <a href="https://learn.microsoft.com/en-us/dotnet/maui/get-started/first-app?pivots=devices-windows&view=net-maui-8.0&tabs=visual-studio-code" target="_blank">Microsoft's .NET MAUI documentation</a>.

### Step 2: Install the Telerik UI for .NET MAUI Controls

The `Telerik.UI.for.Maui` package is available on the public <a href="https://www.nuget.org/packages/Telerik.UI.for.Maui" target="_blank">NuGet.org</a> registry (recommended) and on the authenticated Telerik NuGet server.

Navigate to your project's root directory in the terminal and run:

```bash
dotnet add package Telerik.UI.for.Maui
```

### Step 3: Add the Telerik Namespace and Register the Controls

@[template](/_contentTemplates/get-started.md#add-namespace-register-controls)

### Step 4: Add a Telerik UI Component

@[template](/_contentTemplates/get-started.md#add-telerik-component)

</TabStripTab>
</TabStrip>

## Next Steps

@[template](/_contentTemplates/common/see-also.md#see-also)

