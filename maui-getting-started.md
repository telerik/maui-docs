---
title: Getting Started
page_title: Getting Started with Telerik .NET MAUI controls
description: Getting Started with .NET MAUI - Telerik UI controls for .NET MAUI
slug: maui-getting-started
tags: .net maui, ui for .net maui, .net maui controls
position: 1
---

# Getting Started

This article will guide you through the basics of Telerik UI for .NET MAUI and how to start using the product.

## Getting Started with .NET MAUI

Information about what are the exact steps to get started with Microsoft .NET MAUI and what are the system requirements are described inside the [Microsoft .NET MAUI Documentation page](https://docs.microsoft.com/en-us/dotnet/maui/get-started/installation)

## Getting Started with Telerik UI for .NET MAUI

Once you have .NET MAUI configured on your machine, then follow the steps needed to set up the Telerik UI for .NET MAUI. 

>important Run `maui-check`. It is required for using Telerik UI for MAUI controls and build and run the DemoApp.

>important Telerik .NET MAUI Preview controls are available for Android, iOS, macOS and WinUI.

## Download product files from Telerik UI for .NET MAUI product page

**1. Log into your [Telerik Account](https://www.telerik.com/account/).**

**2. Go to [Telerik UI for MAUI product page](https://www.telerik.com/maui-ui)**

**3. Click Download Telerik UI for .NET MAUI button:**

![Telerik UI for .NET MAUI](images/download_maui.png)

**4. The download starts automatically**

![Telerik UI for .NET MAUI](images/downloading-maui.png)

## Download product files from your Telerik Account

**1. Log into your [Telerik Account](https://www.telerik.com/account/).**

**2. Click on the __Downloads__ tab:**

![Telerik UI for .NET MAUI](images/download-tab.png)

**3. Search maui and Select __Telerik UI for .NET MAUI__ product title:**

![Telerik UI for .NET MAUI](images/search-for-maui.png)

**4. The next page allows you to download the Automatic Installations .msi file, .pkg file and Telerik .NET MAUI NuGet Package:**

![Telerik UI for .NET MAUI](images/product-files.png)

## Installation for Windows

* Telerik_UI_for_Maui_[version]_Preview.msi - runnable msi file used for automatic installation (for use on PC). Run the MSI file and follow the instructions. On a 32bit machine the wizard will install the UI for MAUI component in the following folder unless you specify otherwise: C:\Program Files\Progress\ or C:\Program Files (x86)\Progress\ for a 64bit machine.

The installation folder has the following subdirectories:

![Telerik UI for MAUI Installation Folder](images/telerik-ui-for-maui-installation-folder.png)

* Binaries - Contains the needed dlls for Android and iOS 
* SDKBrowser - Demo App with Telerik UI for .NET MAUI controls
* LicenseAgreements - provides the product EULA.
* Packages - Telerik_UI_for_Maui_[version]_Preview.nupkg file

## Installation for macOS

* Telerik_UI_for_Maui_[version]_Preview.pkg - runnable pkg file used for automatic installation (for use on Mac).

The installation folder has the following subdirectories:

![Telerik UI for .NET MAUI Installation Folder](images/installation-macos.png)

* Binaries - Contains the needed dlls for Android and iOS 
* SDKBrowser - Demo App with Telerik UI for .NET MAUI controls
* LicenseAgreements - provides the product EULA.
* Packages - Telerik_UI_for_Maui_[version]_Preview.nupkg file

## NuGet Package

* Telerik_UI_for_Maui_[version]_Preview.nupkg file for Windows and macOS users.

The Telerik UI for .NET MAUI Nuget Package is available in the **Telerik NuGet Server**.

![Telerik UI for MAUI Installation Folder](images/maui-nuget.png)

## Register the needed handlers and renderers

In order to visualize the Telerik UI for .NET MAUI controls you have to register the needed renderers Register the Telerik controls through `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `Configure` method of the **Startup.cs** file of your project. 

1. Add the needed usings inside the `Startup.cs` file:

```C#
using Telerik.Maui.Controls.Compatibility;
```

2. Call `UseTelerik()` method inside the `Startup.cs` file:


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

## SDKBrowser Maui Demo Application

Telerik UI for .NET MAUI.Preview version comes with a sample app, which demonstrates the Telerik Preview controls for Microsoft .NET MAUI. For more details visit our [Demo App article]({%slug maui-demo-app%}).

## See Also

* [Border]({%slug border-overview%})
* [Button]({%slug button-overview%})
* [Chart]({%slug chart-overview%})
* [ItemsControl]({%slug itemscontrol-overview%})
