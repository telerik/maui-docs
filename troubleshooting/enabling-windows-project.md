---
title: How To Enable Windows Project
page_title: Enabling the Windows MAUI Project
description: Tutorial on how to enable the Windows project in a .NET MAUI project.
tags: .net maui, maui, windows, WinUI, TFM
slug: enable-windows-project
---

# Problem

In .NET 6 RC1, you can now use a single project for all the MAUI target platforms. This means you no longer need an external WinUI project.  However, this is not currently enabled by default, there are some configuration steps needed. 

> This is expected to be fixed in future releases of Visual Studio 2022 and .NET 6.

## Setup

The first thing you need to do is make sure you have the prerequisite tooling installed, let's cover those quickly.

### 1. Visual Studio 2022 Preview 4 with the .NET MAUI Workload

When installing Visual Studio 2022, make sure the .NET MAUI tools are selected underneath the *optional* section.

![](../images/troubleshooting/vs2022-preview4-maui-installer.png)

> Visit the official blog post on the topic [Update on .NET Multi-platform App UI .NET MAUI](https://devblogs.microsoft.com/dotnet/update-on-dotnet-maui/) and carefully read the instructions.

### WinUI Tooling

Next, you need to get something that doesn't come with Visual Studio yet. Download and install the [Single Project MSIX Packaging Tools](https://marketplace.visualstudio.com/items?itemName=ProjectReunion.MicrosoftSingleProjectMSIXPackagingToolsDev17) VSExtension to Visual Studio 2022.

## Solution

Let's start with a brand new .NET MAUI project (*Visual Studio > File > New project > select .NET MAUI App*).

![](../images/troubleshooting/maui-project-template.png)

At this point, you should have a MAUI project with `Android`, `iOS`, `MacCatalyst` and `Windows` listed under the **Platforms** folder. However, the Windows Platform doesn't have a TFM enabled so there's no way to build and deploy a Windows app.

Take the following steps to fix this.

### 1. Enable the Windows TFM

To enable the Windows platform, you'll need to manually edit the **.csproj** file and uncomment the following line:

![](../images/troubleshooting/windows-tfm-in-csproj.png)

Make sure you *save the csproj file immediately* and let the project reload itself. After it is done reloading, you should now see a `net6.0-windows10.0.19041` TFM in the dependencies list:

![](../images/troubleshooting/windows-tfm-in-solution-explorer.png)

### 2. Deploy a Windows Project

Now that you have a Windows platform in the project, we need to configure Visual Studio to Deploy. Expand the target platform and change to **Windows Machine** and change the Framework to `net6.0-windows10.0.19041`:

![](../images/troubleshooting/selecting-windows-tfm-target.png)

Now, you can build and deploy the WinUI project to the local PC:

![](../images/troubleshooting/windows-deployed.png)




