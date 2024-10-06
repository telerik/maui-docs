---
title: Automated Installer
page_title: Ways to Install Telerik UI for .NET MAUI
description: Learn more about the available approaches to install the Telerik UI for .NET MAUI product files, assemblies, and controls on Windows and macOS by using the MSI or PKG files, or the Telerik NuGet server.
slug: automated-installer
tags: .net maui, ui for .net maui, automatic installation, installer
position: 4
---

# Automated Installer for Telerik UI for .NET MAUI

You can use Telerik UI for .NET MAUI on Windows and macOS. Depending on the operation system you are using and on the preferred way to work with the product, the suite can be installed in the following ways:

* [(Windows) MSI file installation](#msi-file-installation)
* [(macOS) PKG file installation](#pkg-file-installation)

## MSI File Installation

MSI files are intended to provide an automatic installation experience of a product on Windows machines. The Telerik UI for .NET MAUI MSI file installs the controls on your computer in a `Program Files/Progress` folder and automatically creates the necessary virtual folders and projects.

You can download the MSI automated installer from the [Downloads](https://www.telerik.com/account/downloads/product-download?product=MAUI) section of your Telerik account. Go to [Available Product Files]({%slug download-product-files%}) topic for detailed steps on how to navigate to the product download page.

Alternatively, you can [install a Free Trial version]({%slug install-trial%}) of Telerik UI for .NET MAUI on your machine.

Now, you are all set to start with the installation:

1. Run the `Telerik_UI_for_dot_NET_Maui_[version]_[license].msi` file and follow the instructions. The file automatically installs Telerik UI for .NET MAUI on your PC.

    ![Telerik UI for .NET MAUI MSI Installer](images/msi-installer.png)

    On a 32-bit machine, the wizard will suggest to install the UI for .NET MAUI controls in `C:\Program Files\Progress\`. On a 64-bit machine, the wizard will suggest to install the UI for .NET MAUI controls in `C:\Program Files (x86)\Progress\`.

1. Use the subdirectory of the installation folder you need:

    * `Binaries`&mdash;Contains the `Net8` and `Net9` folders. Each folder contains the needed assemblies for Android, iOS, MacCatalyst, and WinUI.
    * `Examples`&mdash;Contains the sample applications demonstrating the Telerik UI for .NET MAUI controls. For more details, go to the [Sample Applications]({%slug sampleapps-overview%}) section.
    * `LicenseAgreements`&mdash;Provides the product End-User License Agreement (EULA).
    * `Packages`&mdash;Contains the `Telerik.UI.for.Maui.[version].nupkg` file as well as the Document Processing NuGet packages.
	* `VSExtensions`&mdash;Contains the Visual Studio Extension for Visual Studio 2022.

    ![Telerik .NET MAUI Installation folder with the displayed subdirectories](../images/telerik-ui-for-maui-installation-folder.png)

## PKG File Installation

PKG files are intended to provide an automatic installation experience of a product on Mac machines. The Telerik UI for .NET MAUI PKG file installs the controls on your computer in a `Documents/Progress` folder.

Now, you are all set to start with the installation on your machine from the Apple Installer `.pkg` file:

1. Run the `Telerik_UI_for_dot_NET_Maui_[version].pkg` file and follow the instructions. As a result, the file will automatically install Telerik UI for .NET MAUI on your Mac.

    ![Telerik UI for .NET MAUI PKG Installer](images/pkg-installer.png)

1. Use the sub-directory of the installation folder you need:

    * `Binaries`&mdash;Contains the `Net8` and `Net9` folders. Each folder contains the needed assemblies for Android, iOS, MacCatalyst, and WinUI.
    * `Examples`&mdash;Contains the sample applications demonstrating the Telerik UI for .NET MAUI controls. For more details, go to the [Sample Applications]({%slug sampleapps-overview%}) section.
    * `LicenseAgreements`&mdash;Provides the product End-User License Agreement (EULA).
    * `Packages`&mdash;Contains the `Telerik.UI.for.Maui.[version].nupkg` file as well as the Document Processing NuGet packages.
    * `VSExtensions`&mdash;Contains the Visual Studio Extension for Visual Studio 2022.
    
    ![Telerik UI for .NET MAUI Installation dialog on macOS with the welcome message](../installation/mac/images/mac-folders.png)

# See Also

- [Available Product Files]({%slug download-product-files%})
- [install a Free Trial version]({%slug install-trial%}) 
- [Sample Applications]({%slug sampleapps-overview%})