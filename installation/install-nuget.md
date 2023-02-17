---
title: Installing with NuGet
page_title: Telerik .NET MAUI Installation with NuGet Server and VS for Windows
description: "Get started with Telerik UI for .NET MAUI and learn how to install the controls by using the Telerik NuGet Server with Visual Studio for Windows."
tags: maui, dotnet maui, microsoft maui, telerik maui, nuget, ui for .net maui
slug: telerik-nuget-server
position: 30
previous_url: /telerik-nuget-server, /get-started/install-nuget
---

# Installing Telerik UI for .NET MAUI by Using the Telerik NuGet Server

NuGet is a popular .NET package manager. Progress maintains the Telerik NuGet Feed for registered users and you can include the Telerik UI for .NET MAUI suite in your solution and/or update to the latest available version from there as well. Installing the Telerik UI for .NET MAUI library with NuGet works both for Windows and MacOS machines.

The following video demonstrates how to register the feed on your system and add the product package you need by using visual Studio for Windows.  

<iframe width="560" height="315" src="https://www.youtube.com/embed/c3m_BLMXNDk" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

>important The `Telerik.UI.for.Maui` NuGet works with .NET 6.0 and .NET 7.0 projects. It automatically restore the needed packages depending on the .NET version used in the project.

## Prerequisites

To access the Telerik NuGet server, use your [Telerik Account](https://www.telerik.com/account) login credentials.

## Registering the Feed on Your System

To add the Telerik server to the NuGet package sources:

1. Go to **Tools** > **Package Manager Settings**.

  ![Telerik NuGet Package](images/nuget-vs-pm-settings.png)

1. Open the **Package Sources** section.

  ![Telerik NuGet Package](images/nuget-vs-add-source.png)

1. In the **Source** field, add the Telerik server by filling in its URL: [https://nuget.telerik.com/v3/index.json](https://nuget.telerik.com/v3/index.json). Click **Update**.

  Note that the [https://nuget.telerik.com/v3/index.json](https://nuget.telerik.com/v3/index.json) server will be deprecated and you are recommended to switch to the v3 API, which is faster and more lightweight, and also reduces the number of requests from NuGet clients.

  ![Telerik NuGet Package](images/nuget-vs-telerik-server.png)

The Telerik server is now ready to use. You can go to your solution and open the **Solution Package Manager**.

## Installing the Telerik UI .NET MAUI Package

To install the `Telerik.UI.for.Maui` package to your projects:

1. Select the Telerik server as a package source and enter your credentials when prompted.
1. Search for the `Telerik.UI.for.Maui` package.
1. Select the package.
1. Select the projects which require the package.
1. Select the version and click **Install**.

![Telerik .NET MAUI Package](images/maui-nuget.png)

## See Also

- [Telerik UI for .NET Sample Applications]({% slug sampleapps-overview %})
