---
title: Getting Started
page_title: Getting Started with Telerik UI for MAUI Controls
description: "Get started with Telerik UI controls for .NET MAUI."
slug: maui-getting-started
tags: .net maui, ui for .net maui, .net maui controls
position: 1
---

# Getting Started with Telerik UI for MAUI

This guide provides the information you need to start using the Telerik UI for MAUI suite&mdash;it includes instructions about the available installation approaches, the required dependencies, the code for running the project, and links to additional resources.

After the completion of this guide, you will be able to achieve an end result as demonstrated in the following example.

(demo/screenshot)

## Setting Up Your Microsoft Project

Before you start with the installation of any Telerik UI for MAUI control, ensure that you have a running Microsoft project. The prerequisites to accomplish the installation of the components are always the same regardless of the Telerik UI for MAUI component you want to use, and are fully described in the [official Microsoft documentation](https://docs.microsoft.com/en-us/dotnet/maui/get-started/installation).

Once the Microsoft project is set up, run `maui-check`. The command builds and runs the Telerik UI for MAUI Demo App and is required by the Telerik UI for MAUI controls.

## Downloading Telerik UI for MAUI

You can choose to use either of the following approaches for downloading the Telerik UI for MAUI product files:

* [Telerik UI for MAUI product page](https://www.telerik.com/maui-ui)
* [Your Telerik account](https://www.telerik.com/account/)

### Downloading from Telerik UI for MAUI Product Page

1. Log into your [Telerik Account](https://www.telerik.com/account/).
1. Go to the [Telerik UI for MAUI product page](https://www.telerik.com/maui-ui)
1. Click the **Download Telerik UI for MAUI** button:

  ![Telerik UI for .NET MAUI](images/download_maui.png)

1. As a result, the download starts automatically.

  ![Telerik UI for .NET MAUI](images/downloading-maui.png)

### Downloading from Your Telerik Account

1. Log into your [Telerik Account](https://www.telerik.com/account/).
2. Click the `Downloads` tab:

  ![Telerik UI for .NET MAUI](images/download-tab.png)

1. Search `maui` and select the **Telerik UI for MAUI** product title:

  ![Telerik UI for .NET MAUI](images/search-for-maui.png)

1. The page that loads next allows you to download the `.msi` and `.pkg` files for automatic installation and the Telerik .NET MAUI NuGet package:

  ![Telerik UI for .NET MAUI](images/product-files.png)

## Installing Telerik UI for MAUI

Depending on whether you work with Windows or MacOS on your machine, use the corresponding approach to install Telerik UI for MAUI:

* [Installation for Windows](#installation-for-windows)
* [Installation for MacOS](#installation-for-macos)
* [Installation for Windows and MacOS with NuGet](#installation-with-nuget)

### Installation for Windows

`Telerik_UI_for_Maui_[version]_Preview.msi` is a runnable `.msi` file that is used for automatic installation on PC only. Run the file and follow the instructions.

Unless you specify otherwise, the wizard will install the Telerik UI for MAUI component in the following folders:

* (On 32bit machines) `C:\Program Files\Progress\`
* (On 64bit machines) `C:\Program Files (x86)\Progress\`

The installation folder provides the following subdirectories:

* `Binaries`&mdash;Contains the needed dlls for Android and iOS.
* `DemoApp`&mdash;Contains the Demo App with Telerik UI for .NET MAUI controls.
* `LicenseAgreements`&mdash;Provides the product EULA.
* `Packages`&mdash;Contains the `Telerik_UI_for_Maui_[version]_Preview.nupkg` file.

![Telerik UI for MAUI Installation Folder](images/telerik-ui-for-maui-installation-folder.png)

## Installation for MacOS

`Telerik_UI_for_Maui_[version]_Preview.pkg` is a runnable `.pkg` file that is used for automatic installation Mac only.

The installation folder provides the following subdirectories:

* `Binaries`&mdash;Contains the needed dlls for Android and iOS.
* `DemoApp`&mdash;Contains the Demo App with Telerik UI for .NET MAUI controls.
* `LicenseAgreements`&mdash;Provides the product EULA.
* `Packages`&mdash;Contains the `Telerik_UI_for_Maui_[version]_Preview.nupkg` file.

![Telerik UI for MAUI Installation Folder](images/installation-macos.png)

### Installation with NuGet

The `Telerik_UI_for_Maui_[version]_Preview.nupkg` file is intended both for Windows and MacOS users. The Telerik UI for MAUI NuGet package is available in the **Telerik NuGet Server**.

![Telerik UI for MAUI Installation Folder](images/maui-nuget.png)

For more information, refer to the [guide on installing Telerik UI for MAUI with the Telerik NuGet Server]({% slug telerik-nuget-server %}).

## Registering Required Handlers and Renderers

To visualize the Telerik UI for MAUI controls, you have to register the required renderers by calling the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method inside the `Configure` method of the `Startup.cs` file of your project.

1. Add the needed usings inside the `Startup.cs` file:

    ```C#
    using Telerik.Maui.Controls.Compatibility;
    ```

2. Call the `UseTelerik()` method inside the `Startup.cs` file:


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

## Running the Demo App

The Telerik UI for MAUI Preview version comes with a sample application which demonstrates the Telerik UI for MAUI Preview controls. For more information, refer to the [Demo App article]({% slug maui-demo-app %}).

## Suggested Links

* [Installing Telerik UI for MAUI with the Telerik NuGet Server]({%slug telerik-nuget-server %})
* [Getting Started with Telerik UI for MAUI Demo App]({% slug maui-demo-app %})
* [Getting Started with Telerik UI for MAUI Barcode]({% slug barcode-overview %})
