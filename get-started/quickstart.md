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
|---|---|---|
| [.NET SDK](https://dotnet.microsoft.com/en-us/download) | 9.0 or later |
| Operating system | Windows or macOS |
| Telerik account | Active subscription or trial license required. |
| IDE | Visual Studio 2022 17.12 or later, or Visual Studio Code with the .NET MAUI workloads installed. |

## Step 1: Set up your Telerik account

To use the Telerik UI for .NET MAUI controls, you need a Telerik account with an active license. If you have an active license, you can skip this step. 

1. Go to the [Telerik UI for .NET MAUI product page](https://www.telerik.com/maui-ui).
    
1. Click the **Get Started** or **Try Now** button.

1. Enter your email address and you will see the registration form.

## Step 2: Set Up Telerik Development Environment

This getting started guide uses the Telerik CLI .NET command tool to set up your development environment. The Telerik CLI is a command-line interface that helps you manage your Telerik account, license, NuGet package sources and Telerik MCP server.

Install the Telerik CLI:

```powershell
dotnet tool install -g Telerik.CLI --source https://api.nuget.org/v3/index.json
```

## Step 3: Set Up Your Telerik .NET MAUI Environment with Telerik CLI

Use the `telerik setup maui` command to set up your Telerik environment:

```powershell
telerik setup maui
```

The `telerik setup maui` command performs all the required setup steps at once:

[x] Logs you into your Telerik account.

[x] Downloads your Telerik license key file and saves `telerik-license.txt` to your operating system user's folder, making it available to all Telerik .NET apps on your machine.

[x] Configures the Telerik NuGet package source.

[x] Installs the Telerik MCP server for AI-powered coding assistance.

## Step 4: Create a New MAUI Project

Choose your preferred IDE to create a new .NET MAUI project and install the Telerik UI for .NET MAUI controls:

> If your project uses the `Telerik.UI.for.Maui.8.0.0` NuGet package and .NET 9, you must also install the `Microsoft.Maui.Controls.Compatibility` package. This is needed because Telerik UI for .NET MAUI version 8.0.0 depends on Microsoft's compatibility package, which is no longer included in the default **.NET MAUI App** project template. This dependency has been removed in Telerik UI for .NET MAUI version 9.0.0.

<TabStrip>
<TabStripTab title="Visual Studio">

### Step 1:

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

### Step 5: Add Custom Content to the TemplatedButton

@[template](/_contentTemplates/get-started.md#add-custom-content)

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

### Step 5: Add Custom Content to the TemplatedButton

@[template](/_contentTemplates/get-started.md#add-custom-content)

</TabStripTab>
</TabStrip>

## Next Steps

@[template](/_contentTemplates/common/see-also.md#see-also)

## See Also

* [Using a Telerik Theme]({%slug themes-overview%})
* [Telerik Font Icons]({%slug telerik-font-icons%})
