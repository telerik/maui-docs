---
title: Getting Started
page_title: Getting Started with Telerik .NET MAUI controls
description: Getting Started with .NET MAUI - Telerik UI controls for .NET MAUI
slug: maui-getting-started
tags: .net maui, ui for .net maui, .net maui controls
position: 1
---

# Getting Started

This guide provides the information you need to start using the Telerik UI for .NET MAUI suite - it includes instructions about the available installation approaches, the required dependencies as well as links to additional resources.

## Setup Your .NET MAUI App

Before you start with the installation of Telerik UI for .NET MAUI, ensure that you have a running .NET MAUI application. Information about what are the exact steps to get started with Microsoft .NET MAUI and what are the system requirements are described inside the [Microsoft .NET MAUI Official Documentation](https://docs.microsoft.com/en-us/dotnet/maui/get-started/installation).

Once you have .NET MAUI configured on your machine, install/run .NET MAUI Check tool - this is a command line utility that verifies your development environment and installs any missing components and workloads. Go to [dotnet-maui-check Github repo](https://github.com/Redth/dotnet-maui-check) for more details on how to install and use the tool.

>important Once you install the missing components, run `maui-check` again to ensure that your environment has the latest tools and SDKs required by .NET MAUI.

## Download Telerik UI for .NET MAUI

>important Telerik .NET MAUI Preview controls are available for Android, iOS, macOS and Windows.

You can choose either of the following approaches for downloading the Telerik UI for .NET MAUI product files:

* [Telerik UI for .NET MAUI product page](#download-from-telerik-ui-for-net-maui-product-page)
* [Your Telerik account](#download-product-files-from-your-telerik-account)

### Download from Telerik UI for .NET MAUI Product Page

**1.** Log into your [Telerik Account](https://www.telerik.com/account/).

**2.** Go to the [Telerik UI for .NET MAUI product page](https://www.telerik.com/maui-ui).

**3.** Click the **Download Telerik UI for .NET MAUI** button:

![Telerik UI for .NET MAUI](images/download_maui.png)

**4.** As a result, the download starts automatically.

![Telerik UI for .NET MAUI](images/downloading-maui.png)

### Download product files from your Telerik Account

**1**. Log into your [Telerik Account](https://www.telerik.com/account/).

**2.** Click on the __Downloads__ tab:

![Telerik UI for .NET MAUI](images/download-tab.png)

**3**. Search maui and Select __Telerik UI for .NET MAUI__ product title:

![Telerik UI for .NET MAUI](images/search-for-maui.png)

**4.** The next page allows you to download the Automatic Installations .msi file, .pkg file and Telerik .NET MAUI NuGet Package:

![Telerik UI for .NET MAUI](images/product-files.png)

## Install Telerik UI for .NET MAUI

* [Installation for Windows](#installation-for-windows)
* [Installation for MacOS](#installation-for-macos)
* [Installation for Windows and MacOS with NuGet](#installation-with-nuget)

### Installation for Windows

**Telerik_UI_for_Maui_[version]_Preview.msi** is a runnable .msi file that is used for automatic installation on PC only. Run the file and follow the instructions.

On a 32bit machine the wizard will suggest to install the Telerik UI for .NET MAUI components in the following folder: C:\Program Files\Progress\ or C:\Program Files (x86)\Progress\ for a 64bit machine.

>important Specify different installation folder with a shorter path. For example install the Telerik UI for .NET MAUI components on **C:\T\** folder. **D:\T\**, etc.
>
>If the path is too long the following error occurs: *Error occurred while restoring NuGet packages: The specified path, file name, or both are too long. The fully qualified file name must be less than 260 characters, and the directory name must be less than 248 characters.*

The installation folder provides the following subdirectories:

![Telerik UI for MAUI Installation Folder](images/telerik-ui-for-maui-installation-folder.png)

* Binaries - Contains the needed assemblies for Android, iOS, MacCatalyst and WinUI
* Examples - SDK App with Telerik UI for .NET MAUI controls
* LicenseAgreements - Provides the product EULA.
* Packages - Telerik_UI_for_Maui_[version]_Preview.nupkg file

### Installation for macOS

**Telerik_UI_for_Maui_[version]_Preview.pkg** is a runnable .pkg file that is used for automatic installation Mac only.

The installation folder provides the following subdirectories:

![Telerik UI for .NET MAUI Installation Folder](images/installation-macos.png)

* Binaries - Contains the needed dlls for Android, iOS and MacCatalyst 
* Examples - SDK App with Telerik UI for .NET MAUI controls
* LicenseAgreements - provides the product EULA.
* Packages - Telerik_UI_for_Maui_[version]_Preview.nupkg file

### Installation with NuGet

**Telerik_UI_for_Maui_[version]_Preview.nupkg** file is intended both for Windows and MacOS users. The Telerik UI for .NET MAUI NuGet package is available in the **Telerik NuGet Server**.

![Telerik UI for MAUI Installation Folder](images/maui-nuget.png)

>For more information, refer to the [guide on installing Telerik UI for .NET MAUI with the Telerik NuGet Server]({% slug telerik-nuget-server %}).

## Register required handlers and renderers

To visualize the Telerik UI for .NET MAUI controls, you have to register the required renderers by calling the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method inside the `Configure` method of the `Startup.cs` file of your project.

**1.** Add the needed usings inside the `Startup.cs` file:

```C#
using Telerik.Maui.Controls.Compatibility;
```

**2.** Call `UseTelerik()` method inside the `Startup.cs` file:


```C#

public class Startup : IStartup
{
    public void Configure(IAppHostBuilder appBuilder)
    {
        appBuilder
            .UseFormsCompatibility()
            .ConfigureFonts(fonts => {
                fonts.AddFont("ionicons.ttf", "IonIcons");
            })
            .UseTelerik()
            .UseMauiApp<App>();            
    }
}
```

## SDKBrowser .NET MAUI Demo Application

Telerik UI for .NET MAUI.Preview version comes with a sample app, which demonstrates the Telerik Preview controls for Microsoft .NET MAUI. For more information, refer to the [Demo App article]({%slug maui-demo-app%}).

## See Also

* [Install Telerik UI for .NET MAUI with the Telerik NuGet Server]({%slug telerik-nuget-server %})
* [Getting Started with Telerik UI for .NET MAUI Demo App]({% slug maui-demo-app %})
* [Getting Started with Telerik UI for .NET MAUI Barcode]({% slug barcode-overview %})