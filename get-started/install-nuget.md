---
title: Installing with NuGet
page_title: Telerik NuGet Server
description: "Get started with Telerik UI for .NET MAUI and learn how to install the controls by using the Telerik NuGet Server."
tags: maui, dotnet maui, microsoft maui, telerik maui, nuget, ui for .net maui
slug: telerik-nuget-server
position: 30
previous_url: /telerik-nuget-server
---

# Installing with NuGet

NuGet is a popular .NET package manager. Progress maintains the Telerik NuGet Feed for registered users and you can include the Telerik UI for .NET MAUI suite in your solution and/or update to the latest available version from there as well.



Run the `Telerik_UI_for_Maui_[version]_Preview.nupkg` file, which automatically installs Telerik UI for .NET MAUI either on your Windows or MacOS. The Telerik UI for .NET MAUI NuGet package is available on the Telerik NuGet Server.

![Telerik UI for MAUI Installation Folder](images/maui-nuget.png)



>important The credentials needed to access Telerik Nuget server are the same you use to log into your [Telerik Account](https://www.telerik.com/account).

## Visual Studio for Windows

<iframe width="560" height="315" src="https://www.youtube.com/embed/c3m_BLMXNDk" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

The first step is to add the Telerik server to the NuGet package sources. This can be done in the Package Manager Settings from the Tools menu.

![](images/nuget-vs-pm-settings.png)

In the Package Sources section you can add new sources.

![](images/nuget-vs-add-source.png)

In the Source field you should fill in the address of the Telerik server (URL: **https://nuget.telerik.com/v3/index.json**) and click the Update button.

> The old [https://nuget.telerik.com/nuget](https://nuget.telerik.com/nuget) server will be deprecated and we encourage our clients to switch to the v3 API. The new v3 API is faster, lighter, and reduces the number of requests from NuGet clients.

![](images/nuget-vs-telerik-server.png)

The Telerik server is now ready to use. You can go to your solution and open the solution package manager.

### Add Telerik UI for .NET MAUI pack in Visual Studio for Windows

Find the **Telerik.UI.for.Maui** package and install it to your projects following these steps:

1. Select the Telerik server as a package source and enter your credentials when prompted.
1. Search for the Telerik.UI.for.Maui package.
1. Select the package when found.
1. Select which projects will have the package installed.
1. Choose the version and click Install.

![](images/maui-nuget.png)

## See Also

- [Demo App]({%slug maui-demo-app%})
