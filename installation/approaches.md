---
title: Installation Approaches
page_title: Ways to Install Telerik UI for .NET MAUI
description: Learn more about the available approaches to install the Telerik UI for .NET MAUI product files, assemblies, and controls on Windows and macOS by using the MSI or PKG files, or the Telerik NuGet server.
slug: installation-approaches
tags: .net maui, ui for .net maui, .net maui controls, dot net maui, telerik .net maui, mac, windows
position: 2
---

# Installation Approaches for Telerik .NET MAUI

You can use Telerik UI for .NET MAUI on Windows and macOS. Depending on your operating system and on the preferred way to work with the product, you can install the UI components suite in several ways:

* [(Windows) MSI file installation](#msi-file-installation)
* [(macOS) PKG file installation](#pkg-file-installation)
* [(Windows & macOS) NuGet installation](#nuget-installation)

Even though it's not recommended, after installing Telerik UI for .NET MAUI, you can still [add the required assemblies manually](#manually-adding-the-required-assemblies).  

## MSI File Installation

MSI files are intended to provide an easy and automatic installation experience of a product on Windows machines. The Telerik UI for .NET MAUI MSI file installs the controls on your computer in a `Program Files/Progress` folder and automatically creates the necessary virtual folders and projects.

Apart from the described in detail approach for [installing the suite from your Telerik account]({% slug maui-getting-started %}), you can also download the product from its product page:

1. Log into your [Telerik Account](https://www.telerik.com/account/).

1. Go to the [Telerik UI for .NET MAUI product page](https://www.telerik.com/maui-ui).

1. Click the **Download Telerik UI for .NET MAUI** button.

  ![Product page for downloading Telerik UI for .NET MAUI](../images/download_maui2.png)

1. As a result, the download starts automatically.

  ![Your UI for MAUI Installer is downloading... page](../images/downloading-maui.png)

## PKG File Installation

PKG files are intended to provide an easy and automatic installation experience of a product on Mac machines. The Telerik UI for .NET MAUI PKG file installs the controls on your computer in a `Program Files/Progress` folder and automatically creates the necessary virtual folders and projects.

For the step-by-step guide, refer to the article on [installing Telerik UI for .NET MAUI on macOS with the PKG installation file]({% slug install-pkg %}).

## NuGet Installation

The NuGet packages are single ZIP files with the `.nupkg` extension that contain the compiled code (DLLs), other related files, and a descriptive manifest that includes information such as the version package number.

* For more information about how to install Telerik UI for .NET MAUI with NuGet on Windows-running machines, refer to the article on [first steps with NuGet on Windows]({% slug telerik-nuget-server %}).
* For more information about how to install Telerik UI for .NET MAUI with NuGet on macOS-running machines, refer to the article on [first steps with NuGet on macOS]({% slug telerik-nuget-server-mac %}).
* For more information about restoring Telerik UI for .NET MAUI NuGet packages in your CI workflow, refer to the article on [using token-based NuGet authentication]({% slug nuget-keys %}).

## Manually Using Assembly References

Apart from the described steps in the getting started guides, you can also use a manual installation approach for referencing the required Telerik UI for .NET MAUI assemblies into your solution. The manual approach is available in the following cases:

* During the MSI installation&mdash;After you have [automatically installed Telerik UI for .NET MAUI with the MSI file]({%slug maui-getting-started %}), the assemblies will be located in the `C:\Program Files\Progress\` (for 32bit machines) or `C:\Program Files (x86)\Progress\` (for 64bit machines) default directory.
* Using the ZIP file - Alternatively, you can download the ZIP file with all the Telerik UI for .NET MAUI assemblies as described in the article on the [available product files]({%slug download-product-files %}). You can then unzip the file to any location on your machine and reference the assemblies from that location.

No matter whether you've used the `.msi` automatic installation or the `zip` file, you'll receive the `Binaries/Net7` and `Binaries/Net8` folders, which contain the Android, iOS, MacCatalyst, and WinUI platform-specific folders with all assemblies you need.

To manually reference the assembly references, create a `libs` folder in your solution folder. Then, copy the content from the desired .NET folder into your "libs" folder (e.g. `Binaries/NET7` copyto-> `libs`). You can now directly reference the DLLs in that `libs` folder instead of the installation folder.

> Visual Studio 2022 does not support differentiating DLL references for each target platform. You must manually edit the `.csproj` file and add conditions for each platform. The `Telerik.Maui.Controls.dll`, `Telerik.Maui.Controls.Compatibility.dll`, and `Telerik.Maui.Core.dll` must be referenced from the platform-specific folders.

```
<ItemGroup>
    <!-- You can keep the SHARED assembly references in here, the document processing assemblies -->
    <Reference Include="..." />
</ItemGroup>

<ItemGroup Condition="$([MSBuild]::GetTargetPlatformIdentifier('$(TargetFramework)')) == 'windows'">
    <!-- Put Windows-only assembly references in here -->
    <Reference Include="Telerik.WinUI.Controls">
      <HintPath>"The dlls location"\WinUI\Telerik.WinUI.Controls.dll</HintPath>
    </Reference>
    <Reference Include="Telerik.Maui.Controls">
      <HintPath>"The dlls location"\WinUI\Telerik.Maui.Controls.dll</HintPath>
    </Reference>
    <Reference Include="Telerik.Maui.Controls.Compatibility">
      <HintPath>"The dlls location"\WinUI\Telerik.Maui.Controls.Compatibility.dll</HintPath>
    </Reference>
    <Reference Include="Telerik.Maui.Core">
      <HintPath>"The dlls location"\WinUI\Telerik.Maui.Core.dll</HintPath>
    </Reference>
</ItemGroup>

<ItemGroup Condition="$([MSBuild]::GetTargetPlatformIdentifier('$(TargetFramework)')) == 'iOS'">
    <!-- Put iOS-only assembly references in here -->
   <Reference Include="Telerik.iOS">
      <HintPath>"The dlls location"\iOS\Telerik.iOS.dll</HintPath>
    </Reference>
    <Reference Include="Telerik.Maui.Controls">
      <HintPath>"The dlls location"\iOS\Telerik.Maui.Controls.dll</HintPath>
    </Reference>
    <Reference Include="Telerik.Maui.Controls.Compatibility">
      <HintPath>"The dlls location"\iOS\Telerik.Maui.Controls.Compatibility.dll</HintPath>
    </Reference>
    <Reference Include="Telerik.Maui.Core">
      <HintPath>"The dlls location"\iOS\Telerik.Maui.Core.dll</HintPath>
    </Reference>
</ItemGroup>

<ItemGroup Condition="$([MSBuild]::GetTargetPlatformIdentifier('$(TargetFramework)')) == 'maccatalyst'">
    <!-- Put MacCatalyst-only assembly references in here -->
   <Reference Include="Telerik.MacCatalyst">
      <HintPath>"The dlls location"\MacCatalyst\Telerik.MacCatalyst.dll</HintPath>
    </Reference>
    <Reference Include="Telerik.Maui.Controls">
      <HintPath>"The dlls location"\MacCatalyst\Telerik.Maui.Controls.dll</HintPath>
    </Reference>
    <Reference Include="Telerik.Maui.Controls.Compatibility">
      <HintPath>"The dlls location"\MacCatalyst\Telerik.Maui.Controls.Compatibility.dll</HintPath>
    </Reference>
    <Reference Include="Telerik.Maui.Core">
      <HintPath>"The dlls location"\MacCatalyst\Telerik.Maui.Core.dll</HintPath>
    </Reference>
</ItemGroup>

<ItemGroup Condition="$([MSBuild]::GetTargetPlatformIdentifier('$(TargetFramework)')) == 'android'">
    <!-- Put Android-only assembly references in here -->
    <Reference Include="Telerik.Android.Chart">
      <HintPath>"The dlls location"\Android\Telerik.Android.Chart.dll</HintPath>
    </Reference>
    <Reference Include="Telerik.Android.Common">
      <HintPath>"The dlls location"\Android\Telerik.Android.Common.dll</HintPath>
    </Reference>
    <Reference Include="Telerik.Android.Data">
      <HintPath>"The dlls location"\Android\Telerik.Android.Data.dll</HintPath>
    </Reference>
    <Reference Include="Telerik.Android.Input">
      <HintPath>"The dlls location"\Android\Telerik.Android.Input.dll</HintPath>
    </Reference>
    <Reference Include="Telerik.Android.List">
      <HintPath>"The dlls location"\Android\Telerik.Android.List.dll</HintPath>
    </Reference>
    <Reference Include="Telerik.Android.Primitives">
      <HintPath>"The dlls location"\Android\Telerik.Android.Primitives.dll</HintPath>
    </Reference>
    <Reference Include="Telerik.Maui.Controls">
      <HintPath>"The dlls location"\Android\Telerik.Maui.Controls.dll</HintPath>
    </Reference>
    <Reference Include="Telerik.Maui.Controls.Compatibility">
      <HintPath>"The dlls location"\Android\Telerik.Maui.Controls.Compatibility.dll</HintPath>
    </Reference>
    <Reference Include="Telerik.Maui.Core">
      <HintPath>"The dlls location"\Android\Telerik.Maui.Core.dll</HintPath>
    </Reference>
</ItemGroup>
```

>important As some of the controls included in Telerik UI for .NET MAUI suite rely on the SkiaSharp rendering library, you must also install the `SkiaSharp.Views.Maui.Controls.Compatibility` NuGet package.

## Referencing Local NuGet Package Files

If you would rather use offline NuGet package files, you'll need to make a copy of the .nupkg files that would normally get restored from the Telerik NuGet server. You will find offline copies of the .nupkg files in the `Packages` folder of the installation directory. 

![.NET MAUI Platforms Packages folders](./images/installation-folders.png)

Create a `local_packages` folder in your solution directory and copy all those nupkg files into it. Once those are copied, you can now add a new PackageSource to your nuget.config that points to that directory. With that package source in the nuget.config, you will see it when using the NuGet Package Manager.

For example:

```
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <packageSources> 
    <PackageSources>
      <add key="telerik_offline" value="../local_packages/" />
  </PackageSources>
</configuration>
```

>note You will have to restart Visual Studio before it recognizes any changes to a nuget.config file or see a newly added nuget.config file.

## See Also

* [MSI Quickstart]({%slug maui-getting-started%})
* [PKG Quickstart]({%slug install-pkg%})
* [Quickstart with NuGet on Windows]({%slug telerik-nuget-server%})
* [Quickstart with NuGet on macOS]({%slug telerik-nuget-server-mac%})
