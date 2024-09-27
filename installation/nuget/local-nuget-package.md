---
title: Setting Up Locally
page_title: Use the Telerik UI for .NET MAUI Controls by Adding the Telerik NuGet Server to Visual Studio Code
description: Learn how to install the controls by using the Telerik NuGet Server with Visual Studio Code.
tags: maui, dot net maui, microsoft maui, telerik maui, nuget, ui for .net maui controls, windows, mac, install, telerik .net maui, visual studio
slug: local-nuget-packages
position: 4
---

# Setting the NuGet Packages Locally

In case you do not want to use the online Telerik NuGet server, you can setting up a local nuget server.

You can setting up the server in Visual Studio,  updating the `nuget.config` file or through the .NET CLI.

Before you start with setting up the Telerik NuGet Server make sure you have a commercial or a trial license for Telerik .NET MAUI.

## Setting Up a Local Telerik NuGet Server in Visual Studio

To configure the Telerik NuGet feed in Visual Studio:

1. Open Visual Studio.
1. Go to **Tools > NuGet Package Manager > Package Manager Settings**

  ![Telerik NuGet Package Manager context menu with the Package Manager Settings option](../../installation/images/nuget-vs-pm-settings.png)

1. Select **Package Sources**, and then click the + button.

  ![Package Sources dialog with the Available package sources field](../../installation/images/nuget-vs-add-source.png)

1. In the **Source** field, add the path to the local package instead of the URL.
1. Click **Update** and then **OK**.

  ![Package Sources field with the checked Telerik NuGet option](../../installation/images/nuget-vs-telerik-server.png)

You have successfully added the Telerik NuGet feed as a Package source.

## Setting Up the NuGet Server in Nuget.Config

An alternative way to add the Telerik NuGet feed is to directly edit the `nuget.config` file. For more details about this config file, see <a href="https://learn.microsoft.com/en-us/nuget/reference/nuget-config-file#packagesources" target="_blank">Microsoft's dedicated article.</a>

To learn more about how this configuration works, see the <a href="https://learn.microsoft.com/en-us/nuget/consume-packages/configuring-nuget-behavior#creating-a-new-config-file" target="_blank"> Common NuGet Configurations article.</a>

To use a `nuget.config` file for the Telerik feed, you need to:

1. Ensure you have the relevant config file: `%AppData%\NuGet\NuGet.Config`. You can create a new one by via the <a href="https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new" target="blank">dotnet new command</a> by calling `dotnet new nugetconfig`.

2. Add the Telerik feed to the `nuget.config` file, and make sure to use plain-text credentials because the .NET Core NuGet tooling does not fully support encrypted credentials. Here is an example of how your config file can look like:

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
    <packageSources>
    <!--To inherit the global NuGet package sources remove the <clear/> line below -->
    <clear />
    <add key="nuget" value="https://api.nuget.org/v3/index.json" />
    <add key="telerik" value="add the path to the local package" />
    </packageSources>
</configuration>
```

The local package does not require authentication, as it is already downloaded from your Telerik account.
