---
title: First Steps with .NET MAUI in Visual Studio
page_title: Get Started with Telerik UI for .NET MAUI in Visual Studio
description: "Get started with Telerik UI for .NET MAUI and learn how to install and use the controls by utilizing the Telerik NuGet Server and Visual Studio."
tags: maui, dotnet maui, microsoft maui, telerik maui, nuget, ui for .net maui, macos, install
slug: maui-getting-started
position: 2
previous_url: /maui-getting-started, /get-started/first-steps, /installation/windows/install-msi, /first-steps, /get-started/windows/first-steps-msi, /get-started/windows/first-steps-nuget
---

# First Steps with Telerik UI for .NET MAUI in Visual Studio

In this tutorial, you will enhance an existing .NET MAUI application by adding a Telerik UI for .NET MAUI control. You will achieve this by using Visual Studio for Windows and utilizing the Telerik NuGet source that will let you download and install Telerik controls.

## Prerequisites

* To download the Telerik UI for .NET MAUI packages, you need a [Telerik account](https://www.telerik.com/account/). If you don't have one, you can [create one](https://www.telerik.com/account/) for free.
* To create the app, you need Visual Studio 2022 17.8 or later with installed .NET MAUI workload.

## Step 0: Start Your Free Trial

@[template](/_contentTemplates/get-started.md#start-free-trial)

## Step 1: Download Telerik MAUI Extension

To use the **Telerik UI for .NET MAUI Create New Project** wizard, install the Telerik UI for .NET MAUI Visual Studio Extension. You can get the extension from:

* <a href="https://marketplace.visualstudio.com/items?itemName=TelerikInc.ProgressTelerikMAUIExtensions" target="_blank">The Visual Studio Marketplace.</a>

## Step 2: Start the Telerik MAUI Extension

To start the wizard, use the [Project](#project-menu) menu.

1. Open Visual Studio and choose the **Create a new project** option.
1. Search for **telerik maui**:

    ![Create a new project dialog with maui in the search field and results](../installation/vs-integration/images/vsextensions_createapp.png)

1. Select one of the supported project templates:

     * **Telerik .NET MAUI App - Configurable Wizard**&mdash;Represents a configurable wizard, which contains various predefined application templates that include the Telerik .NET MAUI suite setup. 
     * **Telerik .NET MAUI Blank App**&mdash;Represents a blank project for creating a .NET MAUI application that includes the Telerik .NET MAUI suite setup.
     * **Telerik .NET MAUI Blank Shell App**&mdash;Creates a blank .NET MAUI Shell application. You can use this project as a .NET MAUI Shell example. In addition, you can use features like Shell Navigation, .NET MAUI Shell flyout, and .NET MAUI Shell tabs. For more details on .NET MAUI Shell, review the official [Microsoft documentation](https://learn.microsoft.com/en-us/dotnet/maui/fundamentals/shell/). 


## Step 3: Configure the Project

1. The next step lets you configure your **Telerik UI for .NET MAUI** project by setting your project name and its location.

    ![Telerik .NET MAUI App configurable wizard initial screen within the Create your new project dialog](../installation/vs-integration/images/vsextensions_configureapp.png)

1. (Optional) When using the **Telerik .NET MAUI App - Configurable Wizard** project template, an additional screen for choosing the predefined application template loads:

    ![Create new project dialog in the wizard with a blank Telerik UI for .NET MAUI app](../installation/vs-integration/images/vsextensions_newproject-selection.png)

Finally, Visual Studio opens the solution, which is pre-configured to use the Telerik UI for .NET MAUI controls and has the `Telerik.UI.for.Maui` NuGet package installed.

## Step 4: Add the Telerik NuGet Server

Telerik maintains a NuGet feed with official UI for .NET MAUI releases and service packs. These packages are available for registered users with an active trial or commercial license. Adding the Telerik NuGet server as a source in Visual Studio lets you download and install Telerik packages containing controls and utilities.

To add the Telerik NuGet source to Visual Studio:

1. In Visual Studio go to **Tools** > **NuGet Package Manager** > **Package Manager Settings**.

1. Select **Package Sources** and then click the **+** button to add a new package source.

1. Enter a **Name** for the new package source, for example, `telerik.com`.

1. Add the `https://nuget.telerik.com/v3/index.json` URL as a **Source**. Click **OK**.

1. Whenever Visual Studio displays a dialog to enter credentials for `nuget.telerik.com`, use your Telerik account email and password.

	![Add the Telerik NuGet Feed in Visual Studio](./images/telerik-nuget-feed.png)

## Step 5: Install the Telerik UI for .NET MAUI Controls

1. In Visual Studio and go to **Tools** > **NuGet Package Manager** > **Manage NuGet Packages for Solution...**.

2. Install the Telerik UI for .NET MAUI package:

  1. Select the `telerik.com` **Package source** that you [added earlier](#step-2-add-the-telerik-nuget-server). As this is a private NuGet feed, you must authenticate 
  with your [Telerik account](https://www.telerik.com/account/) user name and password.

  1. Select the **Browse** tab and enter `MAUI` in the search box.

		* If using a trial license, select the `Telerik.UI.for.Maui.Trial` package.
		* If using a commercial license, select the `Telerik.UI.for.Maui` package.
  
  1. Select the checkbox for the target Project, and then click **Install**.

	 ![Add Telerik UI for .NET MAUI package to the project](./images/gs-select-nuget-package.png)

## Step 6: Add the Telerik Namespace and Register the Controls

@[template](/_contentTemplates/get-started.md#add-namespace-register-controls)

## Step 7: Add a Telerik UI Component

@[template](/_contentTemplates/get-started.md#add-telerik-component)

## Step 8: Add Custom Content to the TemplatedButton

@[template](/_contentTemplates/get-started.md#add-custom-content)

## Next Steps

* [Telerik UI for .NET MAUI Installation Approaches]({% slug installation-approaches %})
* [Restoring NuGet Packages in Your CI Workflow]({% slug nuget-keys %})

## See Also

* [System Requirements]({% slug system-requirements %})
* [Telerik UI for .NET MAUI Product Page](https://www.telerik.com/maui-ui)
