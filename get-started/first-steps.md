---
title: First Steps
page_title: Telerik .NET MAUI - Getting Started
description: "Get started with Telerik UI for .NET MAUI and learn how to configure the .NET MAUI project on your machine, download and install the library, and register the required handlers and renderers."
slug: maui-getting-started
tags: .net maui, ui for .net maui, .net maui controls
position: 10
previous_url: /maui-getting-started
---

# Getting Started

This guide provides the information you need to start using the Telerik UI for .NET MAUI suite&mdash;it includes instructions about the available download and installation approaches as well as the required handlers and renderers you have to register.

## Step 1: Set Up Your .NET MAUI Application

Before you start with the installation of Telerik UI for .NET MAUI, make sure you have a running .NET MAUI application. For more information on the required steps and system requirements, refer to the [Microsoft .NET MAUI official documentation](https://docs.microsoft.com/en-us/dotnet/maui/get-started/installation).

## Step 2: Download Telerik UI for .NET MAUI

Telerik UI for .NET MAUI provides the following approaches to download the library:

* [Using the Telerik UI for .NET MAUI product page](#from-the-product-page)
* [Downloading with your Telerik account](#with-your-telerik-account)

### Using the Product Page

To download Telerik UI for .NET MAUI from its product page:

1. Log into your [Telerik Account](https://www.telerik.com/account/).

1. Go to the [Telerik UI for .NET MAUI product page](https://www.telerik.com/maui-ui).

1. Click the **Download Telerik UI for .NET MAUI** button.

  ![Telerik UI for .NET MAUI](images/download_maui.png)

1. As a result, the download starts automatically.

  ![Telerik UI for .NET MAUI](images/downloading-maui.png)

### Using Your Telerik Account

To download Telerik UI for .NET MAUI from your Telerik account:

1. Log into your [Telerik Account](https://www.telerik.com/account/).

1. Click the __Downloads__ tab.

  ![Telerik UI for .NET MAUI](images/download-tab.png)

1. Search for MAUI and select the __Telerik UI for .NET MAUI__ product title.

  ![Telerik UI for .NET MAUI](images/search-for-maui.png)

1. On the next page, download the `.msi` and `.pkg` automatic installation files, and the Telerik .NET MAUI NuGet Package.

  ![Telerik UI for .NET MAUI](images/product-files.png)

## Step 3: Install Telerik UI for .NET MAUI

Telerik UI for .NET MAUI provides the following installation options:

* [Installing on Windows](#installation-for-windows)
* [Installing on MacOS](#installation-for-macos)
* [Installing with NuGet (for Windows and MacOS)]({% slug telerik-nuget-server %})

### Installation for Windows

To install Telerik UI for .NET MAUI on Windows:

1. Run the `Telerik_UI_for_dot_NET_Maui_[version]_[license].msi` file and follow the instructions. The file automatically installs Telerik UI for .NET MAUI on your PC.

    On a 32-bit machine, the wizard will suggest to install the UI for .NET MAUI controls in `C:\Program Files\Progress\`. On a 64-bit machine, the wizard will suggest to install the UI for .NET MAUI controls in `C:\Program Files (x86)\Progress\`.

1. The installation folder provides the following subdirectories:

     * **Binaries**&mdash;Contains the needed assemblies for Android, iOS, MacCatalyst, and WinUI.
    * **Examples**&mdash;Contains the samples applications demonstrating the Telerik UI for .NET MAUI controls. For more details go to [Sample Applications]({%slug sampleapps-overview%}) topic.
    * **LicenseAgreements**&mdash;Provides the product End-User License Agreement (EULA).
    * **Packages**&mdash;Contains the `Telerik.UI.for.Maui.[version].nupkg` file as well as the Document Processing nuget packages.
	* **VSExtensions**&mdash;Contains VSExtension for Visual Studio 2022.
	
    ![Telerik .NET MAUI Installation Folder](images/telerik-ui-for-maui-installation-folder.png)

### Installation for macOS

To install Telerik UI for .NET MAUI on MacOS:

1. Run the `Telerik_UI_for_dot_NET_Maui_[version].pkg` file and follow the instructions. 
	
	The file automatically installs Telerik UI for .NET MAUI on your Mac.

1. The installation folder provides the following subdirectories:

    * **Binaries**&mdash;Contains the needed assemblies for Android, iOS, MacCatalyst, and WinUI.
    * **Examples**&mdash;Contains the samples applications demonstrating the Telerik UI for .NET MAUI controls. For more details go to [Sample Applications]({%slug sampleapps-overview%}) topic.
    * **LicenseAgreements**&mdash;Provides the product End-User License Agreement (EULA).
    * **Packages**&mdash;Contains the `Telerik.UI.for.Maui.[version].nupkg` file as well as the Document Processing nuget packages.
	* **VSExtensions**&mdash;Contains the Project Wizard for Visual Studio for Mac.
	
	![Telerik .NET MAUI Installation on MacOS](images/mac-folders.png)

## Step 4: Register Required Handlers and Renderers

To visualize the Telerik UI for .NET MAUI controls, you have to register the required renderers by calling the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method inside the `Configure` method of the `MauiProgram.cs` file of your project.

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

## See Also

* [Installing Telerik UI for .NET MAUI with the Telerik NuGet Server]({%slug telerik-nuget-server %})
* [Telerik UI for .NET MAUI Sample Applications]({% slug sampleapps-overview %})