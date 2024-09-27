---
title: Using NuGet.Config
page_title: Use the Telerik UI for .NET MAUI Controls by Adding the Telerik NuGet Server to Visual Studio Code
description: Learn how to install the controls by using the Telerik NuGet Server with Visual Studio Code.
tags: maui, dot net maui, microsoft maui, telerik maui, nuget, ui for .net maui controls, windows, mac, install, telerik .net maui, visual studio
slug: nuget-config
position: 3
---

# Setting Up the Telerik NuGet Source Editing the NuGet.Config File

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
    <add key="telerik" value="https://nuget.telerik.com/v3/index.json" />
    </packageSources>
    <packageSourceCredentials>
    <telerik>
        <add key="Username" value="your telerik account email" />
        <add key="ClearTextPassword" value="your plain text password" />
    </telerik>
    </packageSourceCredentials>
</configuration>
```

> Adding the password directly in the `nuget.config` is not a recommended approach. Instead you can generate a [nuget key]({%slug nuget-keys%}#generating-nuGet-keys).

## Troubleshooting

See the [NuGet Troubleshooting]({%slug troubleshooting-nuget-feed%}) article for tips about common pitfalls when working with the Telerik NuGet feed.