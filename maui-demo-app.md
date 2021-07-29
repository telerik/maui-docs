---
title: Demo App
page_title: Telerik .NET MAUI Examples
description: .NET MAUI - Telerik UI controls for .NET MAUI
slug: maui-demo-app
tags: .net maui, ui for .net maui, .net maui controls
position: 3
---

#  Telerik UI for MAUI Demo Application

![Telerik UI for MAUI Demo App](images/demo-maui.gif)

## Where is the DemoApp location:

**1. Log into your [Telerik account](https://www.telerik.com/account/).**

**2. Go to [Telerik UI for MAUI product page](https://www.telerik.com/maui-ui)**

**3. Click Download Telerik UI for MAUI button:**

![Telerik UI for .NET MAUI](images/download_maui.png)

**4. The download starts automatically**

![Telerik UI for .NET MAUI](images/downloading-maui.png)

**Installation for Windows**

>important `maui-check --preview` is required for using Telerik UI for MAUI controls and build and run the DemoApp.

* Telerik_UI_for_Maui_[version]_Preview.msi - runnable msi file used for automatic installation (for use on PC). Run the MSI file and follow the instructions. On a 32bit machine the wizard will install the UI for MAUI component in the following folder unless you specify otherwise: C:\Program Files\Progress\ or C:\Program Files (x86)\Progress\ for a 64bit machine.

The DemoApp folder is inside the installation folder. The Installation folder has the following subdirectories:

![Telerik UI for MAUI Installation Folder](images/telerik-ui-for-maui-installation-folder.png)

* Binaries - Contains the needed dlls for Android, iOS and WinUI
* **DemoApp** - Demo App with Telerik UI for .NET MAUI controls
* LicenseAgreements - provides the product EULA.
* Packages - Telerik_UI_for_Maui_[version]_Preview.nupkg file

**Installation for macOS**

>important `maui-check --preview` is required for using Telerik UI for MAUI controls and build and run the DemoApp.

* Telerik_UI_for_Maui_[version]_Preview.pkg - runnable pkg file used for automatic installation (for use on Mac).

The DemoApp folder is inside the installation folder. The installation folder has the following subdirectories:

![Telerik UI for MAUI Installation Folder](images/installation-macos.png)

* Binaries - Contains the needed dlls for Android, iOS and WinUI
* **DemoApp** - Demo App with Telerik UI for .NET MAUI controls
* LicenseAgreements - provides the product EULA.
* Packages - Telerik_UI_for_Maui_[version]_Preview.nupkg file

## Run Demo App using Visual Studio Code for Windows

* Open the HelloMaui folder in Visual Studio Code

![Telerik UI Maui Demo App VS Code](images/maui-app-vs-code-windows.png)

* Wait the project to restore

* Install for example additional extention like Comet for .NET Mobile which allows you to build and launch the app on emulator, etc.

* Select Project's Target Framework

![Telerik UI Maui Demo App VS Code](images/maui-vs-code-options.png)

* Select the emulator/device you want to run the app

## Run on WinUI

* Open the DemoAppWinUI3.sln file in **Visual Studio 2022 Preview**

>important If you want to build and run the app on WinUI you must install the [Single-Project MSIX Packaging Tool for VS 2022 Preview](https://marketplace.visualstudio.com/items?itemName=ProjectReunion.MicrosoftSingleProjectMSIXPackagingToolsDev17)

![Telerik UI for .NET MAUI Demo Application](images/maui-win-ui-project-structure.png)

* Run the Demo app on WinUI

### Demo App on Android

![Telerik UI for .NET MAUI Demo Application](images/demo.png)

### Demo App on iPad

![Telerik UI for .NET MAUI Demo Application](images/demo-ipad.png)

### Demo App on WinUI

![Telerik UI for .NET MAUI Demo Application](images/demo-winui.png)

## See Also

* [Border]({%slug border-overview%})
* [Button]({%slug button-overview%})
* [Chart]({%slug chart-overview%})
* [ItemsControl]({%slug itemscontrol-overview%})
