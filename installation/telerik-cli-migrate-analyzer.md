---
title: Analyze API Changes Before Upgrade
page_title: Telerik CLI migrate analyze - Detect .NET MAUI Breaking Changes
description: Scan Telerik UI for .NET MAUI projects for API breaking changes between versions with the Telerik CLI migrate analyze command.
slug: telerik-cli-migrate-analyzer
tags: telerik, .net maui, ui for .net maui, cli, migrate, analyze, breaking changes, upgrade, upgrading, api compatibility, command line
position: 3
tag: new
components: ["general"]
---

# Detecting .NET MAUI Breaking Changes with Telerik CLI

The `telerik migrate analyze` command of the [Telerik CLI]({%slug telerik-cli%}) scans Telerik UI for .NET MAUI projects and reports API breaking changes between product versions. Run the command before you upgrade a project to find the affected C# and XAML code and to review the recommended changes.

## Benefits of Analyzing Before Upgrading

A newer Telerik UI for .NET MAUI release can include breaking API changes, such as removed or renamed members. Instead of upgrading and fixing compiler errors one at a time, run `telerik migrate analyze` first. The command reports:

* The affected files.
* The exact line and column of each affected member.
* Guidance on how to update the code.

The command uses static analysis, so your project does not need to build successfully first.

## Prerequisites

To use the `telerik migrate analyze` command, install the Telerik CLI as a .NET global tool:

```powershell
dotnet tool install -g Telerik.CLI
```

For more information, see the [Telerik CLI installation steps]({%slug telerik-cli%}#install-the-telerik-cli).

## Analyze a Project

To analyze a project and let the command detect your current Telerik version from the project references, run the following command:

```powershell
telerik migrate analyze --product maui --project ./MyMauiApp.csproj
```

> Version detection works only when the project references Telerik packages or assemblies in a recognizable way. If the command cannot determine your current version, set the `--from-version` option.

## Specify a Version Range

To analyze the changes between two specific versions instead of relying on version detection, use the `--from-version` and `--to-version` options:

```powershell
telerik migrate analyze --product maui --project ./MyMauiApp.csproj --from-version 15.0.0 --to-version 16.0.0
```

## Analyze a Directory

To scan a source directory and its subdirectories without a project file, use the `--directory` option:

```powershell
telerik migrate analyze --product maui --directory ./src --from-version 15.0.0
```

## Analyze Specific Files

To analyze only specific files, use the `--file` option with one or more space-separated paths. The following example analyzes a XAML page and its code-behind file:

```powershell
telerik migrate analyze --product maui --file MainPage.xaml MainPage.xaml.cs --from-version 15.0.0
```

## Get JSON Output

To get machine-readable output for scripts or continuous integration (CI) pipelines, add the `--json` option:

```powershell
telerik migrate analyze --product maui --project ./MyMauiApp.csproj --json
```

## Output Formats

Human-readable output is the console:

```text
Telerik version range: 14.0.0 → 15.0.0
Files discovered: 19, analyzed: 14
Breaking changes found: 4

--------------------------------------------------------------------------------
C:\MyMauiApp\MainPage.xaml
--------------------------------------------------------------------------------
  L18:C9  [TypeRemoved]  PdfFormatProvider
           The type `PdfFormatProvider` has been moved to the new namespace `Telerik.Documents.Fixed.FormatProviders.Pdf.PdfFormatProvider`. Update all usages by changing the namespace from `Telerik.Windows.Documents.Fixed.FormatProviders.Pdf.PdfFormatProvider` to `Telerik.Documents.Fixed.FormatProviders.Pdf.PdfFormatProvider`.
```

JSON output can be used in scripts or CI pipelines to automate the upgrade process. For example, you can parse the JSON output to generate a report or trigger automated code fixes.

```json
{
  "exitCode": 1,
  "message": "Analysis complete (14.0.0 → 15.0.0). 4 breaking change(s) detected.",
  "data": [
    {
      "filePath": "C:\\MyMauiApp\\MyMauiApp\\MainPage.xaml.cs",
      "line": 18,
      "column": 9,
      "typeName": "PdfFormatProvider",
      "member": "",
      "memberKind": "none",
      "changeKind": "typeRemoved",
      "old": "Telerik.Windows.Documents.Fixed.FormatProviders.Pdf.PdfFormatProvider",
      "new": "Telerik.Documents.Fixed.FormatProviders.Pdf.PdfFormatProvider",
      "message": "The type 'PdfFormatProvider' has been moved to the new namespace 'Telerik.Documents.Fixed.FormatProviders.Pdf.PdfFormatProvider'. Update all usages by changing the namespace from 'Telerik.Windows.Documents.Fixed.FormatProviders.Pdf.PdfFormatProvider' to 'Telerik.Documents.Fixed.FormatProviders.Pdf.PdfFormatProvider'.",
      "confidence": "direct"
    }
  ]
}
```

## Save the Report to a File

To save the results to a file for later review, redirect the output.

```powershell
telerik migrate analyze --product winforms --project ./MyMauiApp.csproj --json > findings.json
```

## See Also

* [Install and set up the Telerik CLI]({%slug telerik-cli%})
* [Review the breaking changes in version 16.0.0]({%slug changes-in-16-0-0%})
