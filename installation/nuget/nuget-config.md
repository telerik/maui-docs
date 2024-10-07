---
title: Using NuGet.Config
page_title: Use the Telerik UI for .NET MAUI Controls by Adding the Telerik NuGet Server to Visual Studio Code
description: Learn how to install the controls by using the Telerik NuGet Server with Visual Studio Code.
tags: maui, dot net maui, microsoft maui, telerik maui, nuget, ui for .net maui controls, windows, mac, install, telerik .net maui, visual studio
slug: nuget-config
position: 3
---

# Setting Up the Telerik NuGet Source in NuGet.Config

An alternative way to configure your system to use the Telerik NuGet server is to directly edit the `nuget.config` file. This approach is useful if you don't have Visual Studio installed.

To configure the Telerik NuGet server as a package source directly in the `nuget.config` file:

1. Open the `%AppData%\NuGet\NuGet.Config` file. If the file doesn't exist on your machine, create it by running the `dotnet new nugetconfig` command in the terminal. For more information about the command, see <a href="https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new" target="blank">Microsoft's docs</a>.

2. Add the Telerik feed to the `nuget.config` file. For credentials generate a [nuget key]({%slug nuget-keys%}#generating-nuGet-keys).

```xml
  <configuration>
    <packageSources>
        <clear/>
        <add key="nuget.org" value="https://api.nuget.org/v3/index.json" protocolVersion="3" />
        <add key="MyTelerikFeed" value="https://nuget.telerik.com/v3/index.json" protocolVersion="3"/>
    </packageSources>
    <packageSourceCredentials>
        <MyTelerikFeed>
        <add key="Username" value="api-key" />
        <add key="ClearTextPassword" value="%MY_API_KEY%" />
        </MyTelerikFeed>
    </packageSourceCredentials>
</configuration>
```

For more details about the `NuGet.Config` file, see the following resources:
* <a href="https://learn.microsoft.com/en-us/nuget/reference/nuget-config-file#packagesources" target="_blank">Configuring the NuGet package sources</a>
* <a href="https://learn.microsoft.com/en-us/nuget/consume-packages/configuring-nuget-behavior#creating-a-new-config-file" target="_blank">Creating a new NuGet config file</a>