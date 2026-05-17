---
title: First Steps with .NET MAUI in Visual Studio
page_title: Get Started with Telerik UI for .NET MAUI in Visual Studio
description: "Get started with Telerik UI for .NET MAUI in Visual Studio on Windows — create a .NET MAUI project, add the Telerik NuGet feed, and install the controls."
tags: maui, dotnet maui, microsoft maui, telerik maui, nuget, ui for .net maui, install, visual studio
slug: maui-getting-started
position: 2
previous_url: /maui-getting-started, /get-started/first-steps, /installation/windows/install-msi, /first-steps, /get-started/windows/first-steps-msi, /get-started/windows/first-steps-nuget
---

# First Steps with Telerik UI for .NET MAUI in Visual Studio

This tutorial walks you through the Visual Studio-specific steps for setting up a .NET MAUI project with Telerik UI for .NET MAUI. Before you begin, make sure you have completed the [Quick Start]({%slug maui-quick-start%}) steps for your license and license key.

## Step 1:

1. Open Visual Studio and select **Create a new project** in the start window.

1. Select the **.NET MAUI App** template, and click the **Next** button.

   ![Telerik UI for .NET MAUI - create new MAUI project in Visual Studio](./images/gs-vs-create-maui-app.png)

1. Name your project and select a location.

1. Choose the .NET framework for your project.

1. Wait until Visual Studio restores all dependencies (when done, all exclamation marks in the **Dependencies** tree view item disappear).

1. Click the **Windows Machine** button to build and run the app.

   ![Telerik UI for .NET MAUI - build and run in Visual Studio](./images/gs-vs-build-run.png)

If you encounter any issues creating the basic project, see the complete guide in <a href="https://learn.microsoft.com/en-us/dotnet/maui/get-started/first-app?pivots=devices-windows&view=net-maui-8.0&tabs=vswin" target="_blank">Microsoft's .NET MAUI documentation</a>.

## Step 2: Add the Telerik NuGet Server

Telerik maintains a NuGet feed with official UI for .NET MAUI releases and service packs. These packages are available for registered users with an active trial or commercial license. Adding the Telerik NuGet server as a source in Visual Studio lets you download and install Telerik packages containing controls and utilities.

@[template](/_contentTemplates/common/nuget.md#generate-nuget-key)

Next, add the Telerik NuGet source to Visual Studio:

1. In Visual Studio go to **Tools** > **NuGet Package Manager** > **Package Manager Settings**.

1. Select **Package Sources** and then click the **+** button to add a new package source.

1. Enter a **Name** for the new package source, for example, `telerik.com`.

1. Add the `https://nuget.telerik.com/v3/index.json` URL as a **Source**. Click **OK**.

1. Whenever Visual Studio displays a dialog to enter credentials for `nuget.telerik.com`, use `api-key` as the username and your NuGet API key as the password.

	![Add the Telerik NuGet Feed in Visual Studio](./images/telerik-nuget-feed.png)

## Step 3: Install the Telerik UI for .NET MAUI Controls

1. In Visual Studio go to **Tools** > **NuGet Package Manager** > **Manage NuGet Packages for Solution...**.

1. Install the Telerik UI for .NET MAUI package:

   1. Select the `telerik.com` **Package source** that you [added earlier](#step-2-add-the-telerik-nuget-server). As this is a private NuGet feed, you must authenticate using `api-key` as the username and [your NuGet API key](#step-2-add-the-telerik-nuget-server) as the password.

   1. Select the **Browse** tab, enter `MAUI` in the search box, and then select the `Telerik.UI.for.Maui` package.

   1. Select the checkbox for the target project, and then click **Install**.

   ![Add Telerik UI for .NET MAUI package to the project](./images/gs-select-nuget-package.png)

> If your project uses the `Telerik.UI.for.Maui.8.0.0` NuGet package and .NET 9, you must also install the `Microsoft.Maui.Controls.Compatibility` package. This is needed because Telerik UI for .NET MAUI version 8.0.0 depends on Microsoft's compatibility package, which is no longer included in the default **.NET MAUI App** project template. This dependency has been removed in Telerik UI for .NET MAUI version 9.0.0.

## Step 4: Add the Telerik Namespace and Register the Controls

If your .NET MAUI project uses the default project template provided by Microsoft (not the Telerik project template), you must configure the Telerik namespace, register the controls, and call `UseTelerik`:

@[template](/_contentTemplates/get-started.md#add-namespace-register-controls)

> If your project uses the `Telerik.UI.for.Maui.8.0.0` NuGet package and .NET 9, you must also install the `Microsoft.Maui.Controls.Compatibility` package. This is needed because Telerik UI for .NET MAUI version 8.0.0 depends on Microsoft's compatibility package, which is no longer included in the default **.NET MAUI App** project template. This dependency has been removed in Telerik UI for .NET MAUI version 9.0.0.

## Step 5: Add a Telerik UI Component

@[template](/_contentTemplates/get-started.md#add-telerik-component)

## Step 6: Add Custom Content to the TemplatedButton
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

* [System Requirements]({% slug system-requirements %})
* [Telerik UI for .NET MAUI Product Page](https://www.telerik.com/maui-ui)
