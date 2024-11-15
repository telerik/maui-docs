---
title: Resolving System.IO.FileNotFoundException Cannot Load Microsoft.Maui.Controls.Compatibility When Using .NET 9 And Telerik MAUI Package
description: Learn how to fix the System.IO.FileNotFoundException when using .NET 9 Blank MAUI Project and adding Telerik MAUI Package.
type: troubleshooting
page_title: Fix FileNotFoundException when using .NET 9 Blank MAUI Project and adding Telerik MAUI Package
slug: maui-managed-vtable-types-notsupportedexception
tags: maui, filenotfoundexception, compatibility, net9, dotnet 9
res_type: kb
---

## Environment

| Telerik Version | .NET Version | Product
| --- | --- | --- |
| Telerik UI for MAUI 8.0.0 | NET 9 | Telerik NuGet package |

## Description

This article describes how to resolve the following error: 

```
System.IO.FileNotFoundException: 'Could not load file or assembly 'Microsoft.Maui.Controls.Compatibility, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null'. The system cannot find the file specified.
```

This exception occurs when you are creating a Blank MAUI project that targets .NET 9, and has a reference to the Telerik MAUI package.

## Cause

With .NET 9 official, the compatibility layout classes in the [`Microsoft.Maui.Controls.Compatibility`](https://learn.microsoft.com/en-us/dotnet/maui/whats-new/dotnet-9?view=net-maui-9.0#compatibility-layouts) namespace are obsoleted. The `Microsoft.Maui.Controls.Compatibility` package is removed from the default MAUI Blank app templates.

The exception is related to the fact that the Telerik NuGet package has a reference to the `Microsoft.Maui.Controls.Compatibility` package which package does not exists in the project.

## Solution

To resolve this issue use one of the following approaches:

* Reference the `Microsoft.Maui.Controls.Compatibility` package to the project.
* Reference the Telerik Assemblies Manually&mdash;solution on WinUI.

### Reference the`Microsoft.Maui.Controls.Compatibility` package

Add the`Microsoft.Maui.Controls.Compatibility` package as a reference to the project:

```xml
<ItemGroup>
	<PackageReference Include="Microsoft.Maui.Controls" Version="$(MauiVersion)" />
	<PackageReference Include="Microsoft.Maui.Controls.Compatibility" Version="$(MauiVersion)" />
	<PackageReference Include="Microsoft.Extensions.Logging.Debug" Version="9.0.0" />
	<PackageReference Include="Telerik.UI.for.Maui" Version="8.0.0" />
</ItemGroup>
```

### Reference the Telerik Assemblies Manually - Solution on WinUI.

To add the Telerik references manually, modify the project file (.csproj).

#### Get the Telerik assemblies

@[template](/_contentTemplates/common/manual-packages.md#manual-packages-location)

The `Binaries/Net9` folder contain the Android, iOS, MacCatalyst, and WinUI platform-specific folders with all assemblies you need.

#### Manually reference the assemblies:

**1.** Create a `libs` folder in your solution folder.

**2.** Copy the content of the `Binaries/Net9` folder into your `libs` folder.

**3.** In your solution, reference the DLLs in the `libs` folder.

>Visual Studio 2022 does not support differentiating DLL references for each target platform. You must manually edit the `.csproj` file and add conditions for each platform. The `Telerik.Maui.Controls.dll`, and `Telerik.Maui.Core.dll` must be referenced from the platform-specific folders.

**4.** Reference the Telerik MAUI packages to the .csproj file

```xml
<ItemGroup>
  <!-- You can keep the SHARED assembly references in here, the document processing assemblies -->
  <Reference Include="Telerik.Documents.CMapUtils">
    <HintPath>"The dlls location"\Shared\Telerik.Documents.CMapUtils.dll</HintPath>
  </Reference>
  <Reference Include="Telerik.Documents.Core">
    <HintPath>"The dlls location"\Shared\Telerik.Documents.Core.dll</HintPath>
  </Reference>
  <Reference Include="Telerik.Documents.DrawingML">
    <HintPath>"The dlls location"\Shared\Telerik.Documents.DrawingML.dll</HintPath>
  </Reference>
  <Reference Include="Telerik.Documents.Fixed">
    <HintPath>"The dlls location"\Shared\Telerik.Documents.Fixed.dll</HintPath>
  </Reference>
  <Reference Include="Telerik.Documents.Fixed.FormatProviders.Image.Skia">
    <HintPath>"The dlls location"\Shared\Telerik.Documents.Fixed.FormatProviders.Image.Skia.dll</HintPath>
  </Reference>
  <Reference Include="Telerik.Documents.Flow">
    <HintPath>"The dlls location"\Shared\Telerik.Documents.Flow.dll</HintPath>
  </Reference>
  <Reference Include="Telerik.Documents.Flow.FormatProviders.Doc">
    <HintPath>"The dlls location"\Shared\Telerik.Documents.Flow.FormatProviders.Doc.dll</HintPath>
  </Reference>
  <Reference Include="Telerik.Documents.Flow.FormatProviders.Pdf">
    <HintPath>"The dlls location"\Shared\Telerik.Documents.Flow.FormatProviders.Pdf.dll</HintPath>
  </Reference>
  <Reference Include="Telerik.Documents.Spreadsheet">
    <HintPath>"The dlls location"\Shared\Telerik.Documents.Spreadsheet.dll</HintPath>
  </Reference>
  <Reference Include="Telerik.Documents.Spreadsheet.FormatProviders.OpenXml">
    <HintPath>"The dlls location"\Shared\Telerik.Documents.Spreadsheet.FormatProviders.OpenXml.dll</HintPath>
  </Reference>
  <Reference Include="Telerik.Documents.Spreadsheet.FormatProviders.Pdf">
    <HintPath>"The dlls location"\Shared\Telerik.Documents.Spreadsheet.FormatProviders.Pdf.dll</HintPath>
  </Reference>
  <Reference Include="Telerik.Documents.Spreadsheet.FormatProviders.Xls">
    <HintPath>"The dlls location"\Shared\Telerik.Documents.Spreadsheet.FormatProviders.Xls.dll</HintPath>
  </Reference>
  <Reference Include="Telerik.Documents.SpreadsheetStreaming">
    <HintPath>"The dlls location"\Shared\Telerik.Documents.SpreadsheetStreaming.dll</HintPath>
  </Reference>
  <Reference Include="Telerik.Zip">
    <HintPath>"The dlls location"\Shared\Telerik.Zip.dll</HintPath>
  </Reference>
  <Reference Include="Telerik.Maui.Controls">
    <HintPath>"The dlls location"\Shared\Telerik.Maui.Controls.dll</HintPath>
  </Reference>
  <Reference Include="Telerik.Maui.Core">
    <HintPath>"The dlls location"\Shared\Telerik.Maui.Core.dll</HintPath>
  </Reference>
</ItemGroup>

<ItemGroup Condition="$([MSBuild]::GetTargetPlatformIdentifier('$(TargetFramework)')) == 'windows'">
  <!-- Put Windows-only assembly references in here -->
  <Reference Include="Telerik.Maui.Controls">
    <HintPath>"The dlls location"\WinUI\Telerik.Maui.Controls.dll</HintPath>
  </Reference>
  <Reference Include="Telerik.Maui.Core">
    <HintPath>"The dlls location"\WinUI\Telerik.Maui.Core.dll</HintPath>
  </Reference>
  <Reference Include="Telerik.WinUI.Controls">
    <HintPath>"The dlls location"\WinUI\Telerik.WinUI.Controls.dll</HintPath>
  </Reference>
</ItemGroup>
```

**5.** If you are using Telerik MAUI controls which depend on `SkiaSharp` add the `SkiaSharp.Views.Maui.Controls` package to the project:

```
<ItemGroup>
	<PackageReference Include="Microsoft.Maui.Controls" Version="$(MauiVersion)" />
	<PackageReference Include="Microsoft.Extensions.Logging.Debug" Version="9.0.0" />
	<PackageReference Include="SkiaSharp.Views.Maui.Controls" Version="2.88.9" />
</ItemGroup>
```

#### Register the Telerik controls

To visualize the Telerik controls, register them in the `MauiProgram.cs` file of your project:

**1.** In the `MauiProgram.cs` file, add the following using statement:

```xml
using SkiaSharp.Views.Maui.Controls.Hosting;
using Telerik.Maui.Controls;
```

**2.** In the `CreateMauiApp` method, call the `.UseTelerikControls()` and `.UseSkiaSharp()` extension methods:

```C#
// Code omitted for brevity
.UseMauiApp<App>()
.UseTelerikControls()
.UseSkiaSharp()
// Code omitted for brevity
```
