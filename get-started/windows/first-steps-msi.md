---
title: First Steps with MSI
page_title: Getting Started Guide for Installing with MSI on Windows
description: "Get started with Telerik UI for .NET MAUI and learn how to install the controls from an MSI file, and then build and run a sample application."
slug: maui-getting-started
tags: .net maui, ui for .net maui, .net maui controls, dot net maui, telerik .net maui
position: 1
previous_url: /maui-getting-started, /get-started/first-steps, /installation/windows/install-msi, /first-steps
published: false
---

# First Steps by Installing with the MSI File

The [Telerik .NET MAUI](https://www.telerik.com/maui-ui) library provides an option for installing its controls by downloading and executing the MSI file, which contains the suite.

This tutorial describes how to get up and running with Telerik UI for .NET MAUI by using the automatic MSI installation approach on Windows. Here is the step by step guide you have to follow:

## Step 1: Set Up Your .NET MAUI Project

Before you start with the installation of [Telerik .NET MAUI](https://www.telerik.com/maui-ui), make sure you have a running .NET MAUI application. For more information on the required steps and system requirements, refer to the [Microsoft .NET MAUI official documentation](https://docs.microsoft.com/en-us/dotnet/maui/get-started/installation).

## Step 2: Download Telerik UI for .NET MAUI

Telerik UI for .NET MAUI enables you to download the suite either from the [Telerik .NET MAUI product page](https://www.telerik.com/maui-ui) or through your Telerik account. For the purposes of this tutorial, let's download the batch from your Telerik account:

1. Log into your [Telerik Account](https://www.telerik.com/account/).

1. Click the __Downloads__ tab.

  ![Telerik UI for .NET MAUI Download tab in your account](../../images/download-tab.png)

1. Search for MAUI and select the __Telerik UI for .NET MAUI__ product title.

  ![Telerik UI for .NET MAUI Search field in your account](../../images/search-for-maui.png)

1. On the next page, download the `.msi` automatic installation file.

  ![Telerik UI for .NET MAUI available product files in your account](../../images/product-files.png)

## Step 3: Install Telerik UI for .NET MAUI

Now, you are all set to start with the installation:

1. Run the `Telerik_UI_for_dot_NET_Maui_[version]_[license].msi` file and follow the instructions. The file automatically installs Telerik UI for .NET MAUI on your PC.

    On a 32-bit machine, the wizard will suggest to install the UI for .NET MAUI controls in `C:\Program Files\Progress\`. On a 64-bit machine, the wizard will suggest to install the UI for .NET MAUI controls in `C:\Program Files (x86)\Progress\`.

1. Use the subdirectory of the installation folder you need:

    * `Binaries`&mdash;Contains the `Net7`, `Net8` and `Net9` folders. Each folder contains the needed assemblies for Android, iOS, MacCatalyst, and WinUI.
    * `Examples`&mdash;Contains the sample applications demonstrating the Telerik UI for .NET MAUI controls. For more details, go to the [Sample Applications]({%slug sampleapps-overview%}) section.
    * `LicenseAgreements`&mdash;Provides the product End-User License Agreement (EULA).
    * `Packages`&mdash;Contains the `Telerik.UI.for.Maui.[version].nupkg` file as well as the Document Processing NuGet packages.
	* `VSExtensions`&mdash;Contains the Visual Studio Extension for Visual Studio 2022.

    ![Telerik .NET MAUI Installation folder with the displayed subdirectories](../../images/telerik-ui-for-maui-installation-folder.png)

## Step 4: Register the Required Handlers

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
* [Telerik .NET MAUI Installation Approaches]({% slug installation-approaches %})

## See Also

* [System Requirements for Windows]({% slug system-requirements %})
* [Telerik Toolbox for .NET MAUI on Windows]({% slug toolbox-support %})
* [Telerik Extensions and Project Templates for VS on Windows]({% slug visualstudio-extensions %})
* [Telerik .NET MAUI Product Page](https://www.telerik.com/maui-ui)
