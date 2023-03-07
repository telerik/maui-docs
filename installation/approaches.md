---
title: Installation Approaches
page_title: Ways to Install Telerik UI for .NET MAUI
description: Learn more about the available approaches to install the Telerik UI for .NET MAUI product files, assemblies, and controls on Windows and macOS by using the MSI or PKG files, or the Telerik NuGet server.
slug: installation-approaches
position: 0
---

# Installation Approaches for Telerik UI for .NET MAUI

You can use Telerik UI for .NET MAUI both on Windows and macOS. Depending on the operation system you are using and on the preferred way to work with the product, the suite can be installed in the following ways:

* (Windows) MSI file installation
* (macOS) PKG file installation
* (Windows & macOS) NuGet installation

## Using Project Templates 

Use our [Project Templates]({%slug visualstudio-extensions%}#using-the-telerik-net-maui-app-project-templates) to create a project that has everything setup for you. You can start using our components right away without manually adding the Telerik.Ui.for.Maui nuget package.

	>tip We strongly recommend using project templates. If you choose this option, you can skip the next steps in this article and jump directly to the **Getting Started** topic of any control.

## Manual Installation

You can manually reference the Telerik UI for .NET MAUI assemblies into your project or use the Telerik Nuget packages. For detailed instructions, go to [Step 2: Add references to Telerik Components](#2-add-references-to-telerik-components).

### Manually add required assemblies

If you prefer to manually reference the required Telerik UI for .NET MAUI assemblies into your solution, you can get them in the following ways:

* Through the MSI installation - in this case after [installing Telerik UI for .NET MAUI]({%slug maui-getting-started %}) on your machine, you can find the assemblies in the following default folder: C:\Program Files\Progress\ or C:\Program Files (x86)\Progress\ for a 64bit machine;
* Download a ZIP file containing all the assemblies, for more details on this go to [Download Product Files]({%slug download-product-files %}) topic. You can then unzip the file to any location on your machine and reference the assemblies from that location.

No matter whether you've used the automatic installation or the zip, you'll have Binaries folder has two folders Net6 and Net7 that contain platform-specific folders - Android, iOS, MacCatalyst, WinUI. All assemblies are in these folders. Just need to add the assemblies from these folders to the corresponding platforms' Packages folders inside the .NET MAUI project:

![.NET MAUI Platforms Packages folders](images/platforms-packages.png)

>important As some of the controls included in Telerik UI for .NET MAUI suite rely on **SkiaSharp** rendering library, you should also install **SkiaSharp.Views.Maui.Controls.Compatibility** nuget package.

## MSI File Installation

The MSI files are intended for easy installation of a product on Windows. The Telerik UI for WinUI MSI file installs the controls on your computer in a folder in your Program Files named Progress, and automatically creates the necessary virtual folders and projects.

Apart from the suggested approach to install the suite from your Telerik account, you can also download the product from its product page:

1. Log into your [Telerik Account](https://www.telerik.com/account/).

1. Go to the [Telerik UI for .NET MAUI product page](https://www.telerik.com/maui-ui).

1. Click the **Download Telerik UI for .NET MAUI** button.

  ![Telerik UI for .NET MAUI](images/download_maui.png)

1. As a result, the download starts automatically.

  ![Telerik UI for .NET MAUI](images/downloading-maui.png)

## PKG File Installation

The MSI files are intended for easy installation of a product on Windows. The Telerik UI for WinUI MSI file installs the controls on your computer in a folder in your Program Files named Progress, and automatically creates the necessary virtual folders and projects.

For the step-by-step guide, refer to the article on [installing Telerik UI for .NET MAUI with the `.msi` automatic installation file](link).

## NuGet Installation

The NuGet packages are a single ZIP file with the .nupkg extension that contains the compiled code (DLLs), other related files, and a descriptive manifest that includes information such as the version package number.

    For more information about how to install Telerik UI for WinUI with NuGet, refer to the article on first steps with NuGet.

    For more information about restoring Telerik UI for WinUI NuGet packages in your CI workflow, refer to the article on using token-based NuGet authentication.

## See Also

- [Visual Studio Extensions]({%slug visualstudio-extensions%})
- [Telerik NuGet packages server]({%slug telerik-nuget-server%})
