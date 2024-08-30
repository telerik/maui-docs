---
title: First Steps with .NET MAUI in VS Code
page_title: Get Started with Telerik UI for .NET MAUI in VS Code
description: "Get started with Telerik UI for .NET MAUI and learn how to install and use the controls by utilizing the Telerik NuGet Server and Visual Studio Code."
tags: maui, dotnet maui, microsoft maui, telerik maui, nuget, ui for .net maui, macos, install
slug: get-started-vs-code
position: 2
previous_url: /installation/mac/install-pkg, /get-started/mac/first-steps-nuget, /get-started/mac/first-steps-pkg
---

# First Steps with Telerik UI for .NET MAUI in Visual Studio Code

In this tutorial, you will enhance an existing .NET MAUI application by adding a Telerik UI for .NET MAUI control. You will achieve this by using Visual Studio Code (on Windows or Mac)and utilizing the Telerik NuGet source that will let you download and install Telerik controls.

## Prerequisites

* To download the Telerik UI for .NET MAUI packages, you need a [Telerik account](https://www.telerik.com/account/). If you don't have one, you can [create one](https://www.telerik.com/account/) for free.
* To create the app, you need <a href="https://learn.microsoft.com/en-us/dotnet/maui/get-started/installation?view=net-maui-8.0&tabs=visual-studio-code" target="_blank">Visual Studio Code</a> with the .NET MAUI extension and the <a href="https://learn.microsoft.com/en-us/dotnet/maui/get-started/installation?view=net-maui-8.0&tabs=visual-studio-code#install-net-and-net-maui-workloads" target="_blank">.NET and .NET MAUI workloads</a>.

## Step 0: Start Your Free Trial

* If you already have an [active license](https://www.telerik.com/account/your-licenses) for Telerik UI for .NET MAUI, skip this step and continue with [Step 1](#step-1-set-up-your-net-maui-project).
* If you don't have an active license, follow the steps below to activate your free trial:

	1. [Download](https://www.telerik.com/try/ui-for-maui) the Progress Trial Installer and open the EXE file.

	1. Make sure that **Telerik UI for .NET MAUI** is selected and continue with the setup.

	1. Log in with your Telerik account and complete the installation.

	After the successful installation of .NET MAUI, the Progress Trial Installer activates you 30 day free trial.

<!--How does this work on Mac?-->

## Step 1: Set Up Your .NET MAUI Project

In this step, you will create a basic .NET MAUI project as a starting point for your application development:

<!--The content after this line must be updated.-->

1. Open Visual Studio and select **Create a new project** in the start window.

1. Select the **.NET MAUI App** template, and click the **Next** button.

	![Telerik UI for .NET MAUI - create new MAUI project in Visual Studio](./images/gs-vs-create-maui-app.png)
	
1. Name your project and select a location.

1. Choose the .NET framework for your project.

1. Wait until Visual Studio restores all dependencies (when done, all exclamation marks in the **Dependencies** tree view item disappear).

1. Click the **Windows Machine** button to build and run the app.

	![Telerik UI for .NET MAUI - create new MAUI project in Visual Studio](./images/gs-vs-build-run.png)

If you encounter any issues creating the basic project, see the complete guide in <a href="https://learn.microsoft.com/en-us/dotnet/maui/get-started/first-app?pivots=devices-windows&view=net-maui-8.0&tabs=vswin" target="_blank">Microsoft's .NET MAUI documentation</a>. 

Before you start with the installation of Telerik UI for .NET MAUI, make sure you have a running .NET MAUI application. For more information on the required steps and system requirements, refer to the [Microsoft .NET MAUI official documentation](https://docs.microsoft.com/en-us/dotnet/maui/get-started/installation).

## Step 2: Download Telerik UI for .NET MAUI NuGet Package

Telerik UI for .NET MAUI enables you to download the suite either from the Telerik UI for .NET MAUI product page or through your Telerik account. For the purposes of this tutorial, let's download the batch from your Telerik account:

1. Log into your [Telerik Account](https://www.telerik.com/account/).

1. Click the __Downloads__ tab.

  ![Telerik UI for .NET MAUI Download tab in your account](../../images/download-tab.png)

1. Search for MAUI and select the __Telerik UI for .NET MAUI__ product title.

  ![Telerik UI for .NET MAUI Search field in your account](../../images/search-for-maui.png)

1. On the next page, download the `.nupkg` or `.zip` files. The `.zip` file contains the Telerik .NET MAUI NuGet Package.

  ![Telerik UI for .NET MAUI available product files in your account](../../images/product-files.png)

## Step 3: Add the Telerik NuGet Package Source to Visual Studio for Mac

Now, let's add the Telerik UI for .NET MAUI package through the Telerik NuGet feed. To use the available packages, you need to have an active Telerik account and to authenticate.

1. Click on the solution folder in Visual Studio for Mac to display the context menu and choose **Manage NuGet Packages**.

  ![Telerik NuGet Package Manager context menu with the Package Manager Settings option](../../installation/images/open-manage-nuget-packages-mac.png)

1. Choose the **Configure Source** option from the drop-down in the lower left corner.

  ![Package Sources dialog with the Available package sources field](../../installation/images/getting-started-configure-sources.png)

1. On the next dialog you can see all the available sources. Choose **Add** to add the new server.

  ![Package Sources dialog with the Available package sources field](../../installation/images/getting-started-add-package-source.png)

1. In the **Location** field, add the Telerik server URL: `https://nuget.telerik.com/v3/index.json`. If you use a locally available NuGet package downloaded from [your account](https://www.telerik.com/account/), add the path to the local package instead of the URL. Finally, click **Add Source**.

  ![Package Sources field with the checked Telerik NuGet option](../../installation/images/getting-started-add-telerk-server.png)

> The obsolete NuGet v2 server at `https://nuget.telerik.com/nuget` will be sunset in November 2024. To avoid any interruptions in your development process, change the NuGet server URL to `https://nuget.telerik.com/v3/index.json`.

The Telerik server is now ready to use. You can go to your solution and open the **Solution Package Manager**.

## Step 4: Install the Telerik .NET MAUI NuGet Package

Now, you need to add the Telerik package to the .NET MAUI solution project that you created:

1. Select the Telerik NuGet server as a package source and enter your credentials when prompted.
1. Search for the `Telerik.UI.for.Maui` package and select it.
1. Choose the projects which require the package.
1. Select the desired version and click **Add Package**.

![Manage Packages for Solutions dialog with the search field and the Telerik.UI.for.MAUI package](../../installation/images/telerik-maui-nuget-mac.png)

## Step 5: Register the Required Handlers

To visualize the [.NET MAUI](https://www.telerik.com/maui-ui) controls, you have to register the required handlers by calling the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method inside the `Configure` method of the `MauiProgram.cs` file of your project.

1. Add the needed `using` settings inside the `MauiProgram.cs` file.

 ```C#
using Telerik.Maui.Controls.Compatibility;
 ```

1. Call the `UseTelerik()` method inside the `MauiProgram.cs` file.

 ```C#
public static class MauiProgram
{
	public static MauiApp CreateMauiApp()
	{
		var builder = MauiApp.CreateBuilder();
		builder
			.UseTelerik()
			.UseMauiApp<App>()
			.ConfigureFonts(fonts =>
			{
				fonts.AddFont("OpenSans-Regular.ttf", "OpenSansRegular");
			});

		return builder.Build();
	}
}
 ```

## Next Steps

* [Available Product Files and Assemblies]({% slug download-product-files %})
* [Restoring NuGet Packages in Your CI Workflow]({% slug nuget-keys %})
* [Telerik UI for .NET MAUI Installation Approaches]({% slug installation-approaches %})

## Troubleshooting

This section lists some of the common problems that are observed during NuGet installation.

### Networking Problems

Another common problem is that your machine (PC or DevOps agent) is behind a proxy. To check if you're experiencing a networking issue, open the following URL in your web browser:

https://nuget.telerik.com/nuget/Search()?$filter=IsAbsoluteLatestVersion&searchTerm=%Maui%27&includePrerelease=true&$skip=0&$top=100&semVerLevel=2.0.0. 

After you enter your telerik.com `username` and `password`, you should see an XML search result containing a list of all the `Telerik.UI.for.Maui` packages available with your license.

### Unable to Load the Service Index for Source

The following error may occur if the nuget.telerik.com server is down.

`Unable to load the service index for source https://nuget.telerik.com/v3/index.json`

If you hit that error, make sure that the Telerik NuGet Feed is live at https://status.telerik.com/.

## See Also

* [System Requirements for macOS]({% slug system-requirements-mac %})
* [Telerik Toolbox for .NET MAUI on macOS]({% slug toolbox-support-mac %})
* [Telerik Project Template for VS on macOS]({% slug mac-project-template %})
* [Telerik UI for .NET MAUI Product Page](https://www.telerik.com/maui-ui)
