---
title: First Steps with NuGet
page_title: Windows Getting Started Guide for Installing with Telerik NuGet Server and VS
description: "Get started with Telerik UI for .NET MAUI and learn how to install the controls by using the Telerik NuGet Server with Visual Studio for Windows."
tags: maui, dotnet maui, microsoft maui, telerik maui, nuget, ui for .net maui, windows, install
slug: telerik-nuget-server
position: 2
previous_url: /telerik-nuget-server, /get-started/install-nuget, /installation/install-nuget
---

# First Steps by Installing with the NuGet Package on Windows

NuGet is a popular .NET package manager. Progress maintains the Telerik NuGet Feed for registered users and you can include the Telerik UI for .NET MAUI suite in your project as well as update to the latest available version from there.

While installing Telerik UI for .NET MAUI with NuGet works both for Windows and MacOS machines, this tutorial describes how to get up and running with the library by downloading and installing the controls on Windows. Here is the step by step guide you have to follow:

The following video demonstrates how to register the feed on your system and add the product package you need by using Visual Studio for Windows.  

<iframe width="560" height="315" src="https://www.youtube.com/embed/c3m_BLMXNDk" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

>important The `Telerik.UI.for.Maui` NuGet works with .NET 6.0 and .NET 7.0 projects and automatically restores the required packages depending on the .NET version you are using in your project.

## Step 1: Set Up Your .NET MAUI Project

Before you start with the installation of Telerik UI for .NET MAUI, make sure you have a running .NET MAUI application. For more information on the required steps and system requirements, refer to the [Microsoft .NET MAUI official documentation](https://docs.microsoft.com/en-us/dotnet/maui/get-started/installation).

## Step 2: Download Telerik UI for .NET MAUI

Telerik UI for .NET MAUI enables you to download the suite either from the Telerik UI for .NET MAUI product page or through your Telerik account. For the purposes of this tutorial, let's download the batch from your Telerik account:

1. Log into your [Telerik Account](https://www.telerik.com/account/).

1. Click the __Downloads__ tab.

  ![Telerik UI for .NET MAUI Download tab in your account](../../images/download-tab.png)

1. Search for MAUI and select the __Telerik UI for .NET MAUI__ product title.

  ![Telerik UI for .NET MAUI Search field in your account](../../images/search-for-maui.png)

1. On the next page, download the `.msi` and `.pkg` automatic installation files, and the Telerik .NET MAUI NuGet Package.

  ![Telerik UI for .NET MAUI available product files in your account](../../images/product-files.png)

## Step 3: Add the Telerik NuGet Package Source to Visual Studio

Now, let's add the Telerik UI for .NET MAUI package through the Telerik NuGet feed. To use the available packages, you need to have an active Telerik account and to authenticate.

1. In Visual Studio, select **Tools** > **NuGet Package Manager** > **Package Manager Settings**.

  ![Telerik NuGet Package Manager context menu with the Package Manager Settings option](../images/nuget-vs-pm-settings.png)

1. Select **Package Sources**.

  ![Package Sources dialog with the Available package sources field](../images/nuget-vs-add-source.png)

1. In the **Source** field, add the Telerik server by filling in its [`https://nuget.telerik.com/v3/index.json`](https://nuget.telerik.com/v3/index.json) URL. Click **Update**.

  Note that the [`https://nuget.telerik.com/v3/index.json`](https://nuget.telerik.com/v3/index.json) server will be deprecated and you are recommended to switch to the v3 API, which is faster, more lightweight, and also reduces the number of requests from NuGet clients.

  ![Package Sources field with the checked Telerik NuGet option](../images/nuget-vs-telerik-server.png)

The Telerik server is now ready to use. You can go to your solution and open the **Solution Package Manager**.

## Step 4: Install the Telerik .NET MAUI NuGet Package

Now, you need to add the Telerik package to the .NET MAUI solution project that you created:

1. Select the Telerik NuGet server as a package source and enter your credentials when prompted.
1. Search for the `Telerik.UI.for.Maui` package and select it.
1. Choose the projects which require the package.
1. Select the desired version and click **Install**.

![Manage Packages for Solutions dialog with the search field and the Telerik.UI.for.MAUI package](images/maui-nuget.png)

## Next Steps

* [Available Product Files and Assemblies]({% slug download-product-files %})
* [Restoring NuGet Packages in Your CI Workflow]({% slug nuget-keys %})
* [Telerik UI for .NET MAUI Installation Approaches]({% slug installation-approaches %})

## See Also

* [System Requirements for Windows]({% slug system-requirements %})
* [Telerik Toolbox for .NET MAUI on Windows]({% slug toolbox-support %})
* [Telerik Extensions and Project Templates for VS on Windows]({% slug visualstudio-extensions %})
* [Telerik UI for .NET MAUI Product Page](https://www.telerik.com/maui-ui)
