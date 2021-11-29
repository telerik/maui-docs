---
title: Enabling the Windows Project
page_title: .NET MAUI Knowledge Base | Enabling the Windows .NET MAUI Project
description: "Learn how to enable the Windows project in a Telerik UI for .NET MAUI application."
tags: .net maui, maui, windows, WinUI, TFM
slug: enable-windows-project
type: troubleshooting
ticketid:
publish: false
res_type: kb
---

## Environment

|   |   |
|---|---|
| Product   |Telerik UI for .NET MAUI|
| Product Version | Telerik UI for .NET MAUI 0.0.1 |

## Description

In .NET 6 RC1, you can use a single project for all the MAUI target platforms, which means that you no longer need an external WinUI project.

## Cause

This functionality is not yet enabled by default. To implement it, you need to apply further configuration steps.

> Future Telerik UI for .NET MAUI releases of Visual Studio 2022 and .NET 6 intend to implement the suggested approach out of the box.

## Solution

* [Prerequisites](#prerequisites)
* [Implementation](#implementation)

### Prerequisites

* Install Visual Studio 2022 Preview 4 with the .NET MAUI Workload. Make sure that the .NET MAUI tools are selected from under the **optional** section. For detailed instructions, refer to the official blog post on [updating the .NET Multi-Platform Application](https://devblogs.microsoft.com/dotnet/update-on-dotnet-maui/).

 ![](../images/troubleshooting/vs2022-preview4-maui-installer.png)

* Download and install the [Single Project MSIX Packaging Tools](https://marketplace.visualstudio.com/items?itemName=ProjectReunion.MicrosoftSingleProjectMSIXPackagingToolsDev17) VS Extension to Visual Studio 2022.

### Implementation

1. Go to **Visual Studio** > **File** > **New project** > **.NET MAUI App** and create a new .NET MAUI project.

    ![](../images/troubleshooting/maui-project-template.png)

    On Android, iOS, MacCatalyst, and Windows, the new .NET MAUI project is listed under the **Platforms** folder. However, the Windows Platform doesn't have an enabled TFM and you cannot build and deploy a Windows application.

1. Enable the Windows TFM by manually editing the `.csproj` file. Uncomment the following line:

    ![](../images/troubleshooting/windows-tfm-in-csproj.png)

1. Save the `csproj` file and let the project reload itself. After reloading, a `net6.0-windows10.0.19041` TFM is visible in the dependencies list.

    ![](../images/troubleshooting/windows-tfm-in-solution-explorer.png)

1. Now that you have a Windows platform in the project, configure Visual Studio to deploy. Expand the target platform and change to **Windows Machine**. Change the framework to `net6.0-windows10.0.19041`.

    ![](../images/troubleshooting/selecting-windows-tfm-target.png)

1. Build and deploy the .NET MAUI project to the local PC.

    ![](../images/troubleshooting/windows-deployed.png)
