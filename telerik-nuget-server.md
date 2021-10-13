---
title: Telerik NuGet Server
page_title: Telerik NuGet Server
description: Check our detailed documentation article on how to use Telerik UI for .NET MAUI NuGet package.
tags: maui, dotnet maui, microsoft maui, telerik maui, nuget, ui for .net maui
slug: telerik-nuget-server
position: 2
---

# Telerik NuGet Server

The following steps demonstrate how users can take advantage of **Telerik NuGet server** in order to include our suite in their solution and/or update to the latest available version.

>important The credentials needed to access Telerik Nuget server are the same you use to log into your [Telerik Account](https://www.telerik.com/account).

## Visual Studio for Windows

<iframe width="800" height="400" src="https://www.youtube.com/embed/c3m_BLMXNDk" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

The first step is to add the Telerik server to the NuGet package sources. This can be done in the Package Manager Settings from the Tools menu.

![](images/nuget-vs-pm-settings.png)

In the the Package Sources section users can add new sources.

![](images/nuget-vs-add-source.png)

In the Source field users should fill in the address of the Telerik server (URL: **https://nuget.telerik.com/nuget**) and click the Update button.

![](images/nuget-vs-telerik-server.png)

The Telerik server is now ready to use. Users can go to their solution and open the solution package manager.

### Add Telerik UI for .NET MAUI pack in Visual Studio for Windows

Find the **Telerik.UI.for.Maui** package and install it to their projects following these steps:

1. Select the Telerik server as a package source and enter their credentials when prompted.
1. Search for the Telerik.UI.for.Maui package.
1. Select the package when found.
1. Select which projects will have the package installed.
1. Choose the version and click Install.

![](images/maui-nuget.png)

## See Also

- [Demo App]({%slug maui-demo-app%})
