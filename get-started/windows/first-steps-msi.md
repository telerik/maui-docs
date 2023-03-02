---
title: MSI Quickstart
page_title: First Steps with MSI on Windows
description: "Get started with Telerik UI for .NET MAUI and learn how to install the controls from an MSI file, and then build and run a sample application."
slug: maui-getting-started
tags: .net maui, ui for .net maui, .net maui controls
position: 1
previous_url: /maui-getting-started, /get-started/first-steps, /installation/windows/install-msi
---

# First Steps by Installing with the MSI File

The Telerik UI for .NET MAUI library provides an option for installing its controls by downloading and executing the MSI file, which contains the suite.

This tutorial describes how to get up and running with Telerik UI for .NET MAUI by downloading and installing the controls from an MSI file.

* First, you will set up your .NET MAUI project and create the .NET MAUI application.
* Next, you'll install the Telerik UI for .NET MAUI library from an MSI file, declare the namespace, and define the DataGrid control.
* Then, you will show some sample data in the DataGrid.
* Finally, you will add styles to the DataGrid and populate it with data.

## Step 1: Set Up Your .NET MAUI Project

Before you start with the installation of Telerik UI for .NET MAUI, make sure you have a running .NET MAUI application. For more information on the required steps and system requirements, refer to the [Microsoft .NET MAUI official documentation](https://docs.microsoft.com/en-us/dotnet/maui/get-started/installation).

## Step 2: Download Telerik UI for .NET MAUI

Telerik UI for .NET MAUI enables you to download the suite either from the Telerik UI for .NET MAUI product page or through your Telerik account. For the purposes of this tutorial, let's download the batch from your Telerik account:

1. Log into your [Telerik Account](https://www.telerik.com/account/).

1. Click the __Downloads__ tab.

  ![Telerik UI for .NET MAUI Download tab in your account](images/download-tab.png)

1. Search for MAUI and select the __Telerik UI for .NET MAUI__ product title.

  ![Telerik UI for .NET MAUI Search field in your account](images/search-for-maui.png)

1. On the next page, download the `.msi` and `.pkg` automatic installation files, and the Telerik .NET MAUI NuGet Package.

  ![Telerik UI for .NET MAUI available product files in your account](images/product-files.png)

## Step 3: Install Telerik UI for .NET MAUI

Now, you are all set to start with the installation:

1. Run the `Telerik_UI_for_dot_NET_Maui_[version]_[license].msi` file and follow the instructions. The file automatically installs Telerik UI for .NET MAUI on your PC.

    On a 32-bit machine, the wizard will suggest to install the UI for .NET MAUI controls in `C:\Program Files\Progress\`. On a 64-bit machine, the wizard will suggest to install the UI for .NET MAUI controls in `C:\Program Files (x86)\Progress\`.

1. Use the subdirectory of the installation folder you need:

    * `Binaries`&mdash;Contains the `Net6` and `Net7` folders. Each folder contains the needed assemblies for Android, iOS, MacCatalyst, and WinUI.
    * `Examples`&mdash;Contains the sample applications demonstrating the Telerik UI for .NET MAUI controls. For more details, go to the [Sample Applications]({%slug sampleapps-overview%}) section.
    * `LicenseAgreements`&mdash;Provides the product End-User License Agreement (EULA).
    * `Packages`&mdash;Contains the `Telerik.UI.for.Maui.[version].nupkg` file as well as the Document Processing NuGet packages.
	  * `VSExtensions`&mdash;Contains the Visual Studio Extension for Visual Studio 2022.

    ![Telerik .NET MAUI Installation folder with the displayed subdirectories](images/telerik-ui-for-maui-installation-folder.png)

## Step 4: Register the Required Handlers

To visualize the Telerik UI for .NET MAUI controls, you have to register the required handlers by calling the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method inside the `Configure` method of the `MauiProgram.cs` file of your project.

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

## 1. Start with .NET MAUI app
This article aims to help you set up your application to use **Telerik UI for .NET MAUI** suite on **Windows OS**.
Depending on your scenario, you either have an existing app where you will add our components, or you have to create a new blank app.

### Add Telerik components to an already existing app

You can manually reference the Telerik UI for .NET MAUI assemblies into your project or use the Telerik Nuget packages. For detailed instructions, go to [Step 2: Add references to Telerik Components](#2-add-references-to-telerik-components).

### Create a new app with Telerik UI for .NET MAUI

If you just start your app, you have two options:

- Use our [Project Templates]({%slug visualstudio-extensions%}#using-the-telerik-net-maui-app-project-templates) to create a project that has everything setup for you. You can start using our components right away without manually adding the Telerik.Ui.for.Maui nuget package.

	>tip We strongly recommend using project templates. If you choose this option, you can skip the next steps in this article and jump directly to the **Getting Started** topic of any control.

- Create a new .NET MAUI app in Visual Studio and add the required references to Telerik assemblies.

	If your scenario requires creating a new app from scratch, please proceed following the steps below:

	1. Create a new solution using the **.NET MAUI App** template:

		![Create new .NET MAUI App](images/visual-studio-new-solution.png)

	1. In the next **Configure your new project** window, name your project, choose a suitable location for it.

> For a complete instructions go to [Get Started: Build you first app](https://docs.microsoft.com/en-us/dotnet/maui/get-started/first-app?pivots=devices-android) topic in Microsoft Docs.

## 2. Add references to Telerik Components

You have two options:

### Telerik NuGet package server

You can use our [Telerik NuGet package server]({%slug telerik-nuget-server%}) to include our suite in your solution and/or update to the latest available version.

### Manually add required assemblies

If you prefer to manually reference the required Telerik UI for .NET MAUI assemblies into your solution, you can get them in the following ways:

* Through the MSI installation - in this case after [installing Telerik UI for .NET MAUI]({%slug maui-getting-started %}) on your machine, you can find the assemblies in the following default folder: C:\Program Files\Progress\ or C:\Program Files (x86)\Progress\ for a 64bit machine;
* Download a ZIP file containing all the assemblies, for more details on this go to [Download Product Files]({%slug download-product-files %}) topic. You can then unzip the file to any location on your machine and reference the assemblies from that location.

No matter whether you've used the automatic installation or the zip, you'll have Binaries folder has two folders Net6 and Net7 that contain platform-specific folders - Android, iOS, MacCatalyst, WinUI. All assemblies are in these folders. Just need to add the assemblies from these folders to the corresponding platforms' Packages folders inside the .NET MAUI project:

![.NET MAUI Platforms Packages folders](images/platforms-packages.png)

>important As some of the controls included in Telerik UI for .NET MAUI suite rely on **SkiaSharp** rendering library, you should also install **SkiaSharp.Views.Maui.Controls.Compatibility** nuget package.


## See Also

* [Installing Telerik UI for .NET MAUI with the Telerik NuGet Server]({%slug telerik-nuget-server %})
* [Telerik UI for .NET MAUI Sample Applications]({% slug sampleapps-overview %})
