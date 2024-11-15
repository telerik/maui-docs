---
title: Referencing Assemblies Manually
page_title: Referencing Assemblies Manually
description: Learn how to manually reference the Telerik UI for .NET MAUI assemblies in your solution so you can utilize the Telerik controls.
slug: assembly-references
tags: .net maui, ui for .net maui, .net maui controls, dot net maui, telerik .net maui, mac, windows
position: 20
---


# Referencing Assemblies Manually

Apart from using NuGet packages to install the controls, you can also reference the Telerik UI for .NET MAUI assemblies manually in your solution.

@[template](/_contentTemplates/common/manual-packages.md#manual-packages-location)

The `Binaries/Net8` and `Binaries/Net9` folders contain the Android, iOS, MacCatalyst, and WinUI platform-specific folders with all assemblies you need.

To manually reference the assemblies:

1. Create a `libs` folder in your solution folder.
1. Copy the content of the `Binaries/Net8` or `Binaries/Net9` folder into your `libs` folder.
1. In your solution, reference the DLLs in the `libs` folder.

>important As some of the controls included in Telerik UI for .NET MAUI suite rely on the SkiaSharp rendering library, you must also install the `SkiaSharp.Views.Maui.Controls.Compatibility` NuGet package.

Visual Studio 2022 does not support differentiating DLL references for each target platform. You must manually edit the `.csproj` file and add conditions for each platform. The `Telerik.Maui.Controls.dll`, `Telerik.Maui.Controls.Compatibility.dll`, and `Telerik.Maui.Core.dll` must be referenced from the platform-specific folders.

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

## See Also

- [UI for MAUI Installation Methods]({%slug installation-approaches%})
- [Automated Installer]({%slug automated-installer%})
- [Sample Applications]({%slug sampleapps-overview%})
