---
title: Using Visual Studio Code
page_title: Get Started with Telerik UI for .NET MAUI in VS Code
description: "Get started with Telerik UI for .NET MAUI in Visual Studio Code on Windows or Mac - create a .NET MAUI project, add the Telerik NuGet feed via CLI, and install the controls."
tags: maui, dotnet maui, microsoft maui, telerik maui, nuget, ui for .net maui, macos, install, visual studio code
slug: maui-getting-started-vs-code
position: 3
published: false
previous_url: /installation/mac/install-pkg, /get-started/mac/first-steps-nuget, /get-started/mac/first-steps-pkg
---

# First Steps with Telerik UI for .NET MAUI in Visual Studio Code

This tutorial walks you through the Visual Studio Code-specific steps for setting up a .NET MAUI project with Telerik UI for .NET MAUI on Windows or Mac. Before you begin, make sure you have completed the [Telerik UI for .NET MAUI license and license-key quick start]({%slug maui-quick-start%}).

## Step 1: Create a New MAUI Project

1. Open Visual Studio Code and press `Cmd/Ctrl+Shift+P`. Enter **.NET: New Project...** in the input field.

1. Select the **.NET MAUI App** option.

1. Enter a name for your app.

1. Select an empty folder for your project. If the folder is not empty, the file explorer opens again.

1. Wait for Visual Studio Code to create the project and complete its configuration.

1. Choose the **Debug Target**:

	1. Open a C# or XAML file, for example, `App.xaml`.

	1. Click the curly brackets symbol **{ }** in the bottom right corner of Visual Studio Code.

		* If you are working on a Mac, select **My Mac**.
		* If you are working on Windows, select **Local Machine**.

		![Telerik UI for .NET MAUI - select debug target in Visual Studio Code](./images/gs-vs-code-select-debug-target.png)

1. Press `F5` to start a debug session. If Visual Studio Code prompts you to select a debugger, select C#.

If you encounter any issues creating the basic project, see the Microsoft's guide to [create your first .NET MAUI app in Visual Studio Code](https://learn.microsoft.com/en-us/dotnet/maui/get-started/first-app?pivots=devices-windows&view=net-maui-8.0&tabs=visual-studio-code).

## Step 2: Install the Telerik UI for .NET MAUI Controls

The `Telerik.UI.for.Maui` package is available on the public <a href="https://www.nuget.org/packages/Telerik.UI.for.Maui" target="_blank">NuGet.org</a> registry (recommended) and on the authenticated Telerik NuGet server.

### From NuGet.org (Recommended)

Navigate to your project's root directory in the terminal and run:

```bash
dotnet add package Telerik.UI.for.Maui
```

### From the Telerik NuGet Server (Alternative)

As an alternative, you can install from the authenticated Telerik NuGet server:

@[template](/_contentTemplates/common/nuget.md#generate-nuget-key)

Use the command below to add the Telerik NuGet source. Replace the placeholder with the API key that you generated.

```bash
dotnet nuget add source https://nuget.telerik.com/v3/index.json --name TelerikNuGetFeed --username api-key --password <YOUR-NUGET-API-KEY> --store-password-in-clear-text
```

>See <a href="https://learn.microsoft.com/en-us/nuget/consume-packages/consuming-packages-authenticated-feeds#security-best-practices-for-managing-credentials" target="_blank">Microsoft's security best practices</a> for more information on how to securely store your NuGet source credentials.

Then install the package:

```bash
dotnet add package Telerik.UI.for.Maui --source TelerikNuGetFeed
```

## Step 3: Add the Telerik Namespace and Register the Controls

If your .NET MAUI project uses the default project template provided by Microsoft (not the Telerik project template), you must configure the Telerik namespace, register the controls, and call `UseTelerik`:

@[template](/_contentTemplates/get-started.md#add-namespace-register-controls)

> If your project uses the `Telerik.UI.for.Maui.8.0.0` NuGet package and .NET 9, you must also install the `Microsoft.Maui.Controls.Compatibility` package. This is needed because Telerik UI for .NET MAUI version 8.0.0 depends on Microsoft's compatibility package, which is no longer included in the default **.NET MAUI App** project template. This dependency has been removed in Telerik UI for .NET MAUI version 9.0.0.

## Step 4: Add a Telerik UI Component

@[template](/_contentTemplates/get-started.md#add-telerik-component)

## Step 5: Add Custom Content to the TemplatedButton

@[template](/_contentTemplates/get-started.md#add-custom-content)

## Next Steps

<article-card-container>
	<article-card
		href="/aicomponents"
		src="../images/aicomponents/AIPrompt_Light_Large.svg"
		title="AI Components"
		subTitle="AI Controls & Features"
		darkSrc="../images/aicomponents/AIPrompt_Dark_Large.svg"
		description="Explore the AI-powered controls and features available in Telerik UI for .NET MAUI.">
	</article-card>
	<article-card
		href="/ai/mcp-server"
		src="../images/aicomponents/Chat_Light_Large.svg"
		title="AI Coding Assistant"
		subTitle="MCP Server"
		darkSrc="../images/aicomponents/AI_Data_Operations_Dark_Large.svg"
		description="Use the Telerik MCP server to get AI-assisted coding support for .NET MAUI development.">
	</article-card>
	<article-card
		href="/introduction#list-of-net-maui-ui-controls"
		src="../images/aicomponents/AI_Data_Operations_Light_Large.svg"
		title="Use Controls"
		subTitle="All Controls"
		description="Browse the full list of Telerik UI for .NET MAUI controls available for your application.">
	</article-card>
	<article-card
		href="/demos-and-sample-apps/overview"
		src="../images/getting-started.png"
		title="Sample Applications"
		subTitle="Sample Apps"
		description="Explore sample applications built with Telerik UI for .NET MAUI to see the controls in action.">
	</article-card>
	<article-card
		href="/styling-and-themes/overview"
		src="../front-image.png"
		title="Theming and Styles"
		subTitle="Styling"
		description="Learn how to apply and customize themes across your Telerik UI for .NET MAUI application.">
	</article-card>
	<article-card
		href="/font-icons/examples-icons"
		src="../images/getting-started.png"
		title="Font Icons"
		subTitle="Icons"
		description="Use the built-in Telerik font icons to enhance your .NET MAUI application UI.">
	</article-card>
</article-card-container>


## See Also

* [Review Telerik UI for .NET MAUI System Requirements]({% slug system-requirements %})
* [Explore the Telerik UI for .NET MAUI Product Overview](https://www.telerik.com/maui-ui)
