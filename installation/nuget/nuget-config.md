---
title: Using NuGet.Config
page_title: Using NuGet.Config
description: Install the Telerik UI for .NET MAUI Controls by using the Nuget.Config file to set up the NuGet source.
tags: maui, dot net maui, microsoft maui, telerik maui, nuget, ui for .net maui controls, windows, mac, install, telerik .net maui, visual studio
slug: nuget-config
position: 5
---

# Setting Up the Telerik NuGet Source in NuGet.Config

An alternative way to configure your system to use the Telerik NuGet server is to directly edit the `nuget.config` file. This approach is useful if you don't have Visual Studio installed.

To configure the Telerik NuGet server as a package source directly in the `nuget.config` file, perform the following steps:

1. [Generate a NuGet API key](#generate-a-nuget-key).
1. [Edit the NuGet.Config file](#edit-the-nugetconfig-file).

## Generate a NuGet Key

@[template](/_contentTemplates/common/nuget.md#generate-nuget-key)

## Edit the NuGet.Config File

1. Go to the `NuGet.Config` file:

    * On Windows, open the `%AppData%\NuGet\NuGet.Config` file.
    * On Mac, open either the  `~/.config/NuGet/NuGet.Config` or `~/.nuget/NuGet/NuGet.Config` file (varies by tooling).

    If the file doesn't exist on your machine, create it by running the `dotnet new nugetconfig` command in the terminal. For more information about the command, see <a href="https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new" target="blank">Microsoft's docs</a>.

1. In the `nuget.config` file, add the Telerik feed by inserting the line `<add key="MyTelerikFeed" value="https://nuget.telerik.com/v3/index.json" protocolVersion="3"/>`in the `packageSources` section.

1. In the `packageSourceCredentials` section, add the [generated NuGet API key](#generate-a-nuget-key). Use `api-key` as a value for the user name.

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

## Securing Your NuGet Key

Never hard-code NuGet API keys in a `NuGet.Config` file in a GitHub repository, Docker image, or any location that may be accessed by unauthorized parties. A NuGet key is valuable and bad actors can use it to access the NuGet packages that are licensed under your account. A credentials abuse can lead to a review of the affected Telerik account.

For more details about the `NuGet.Config` file, see the following Microsoft resources:
* <a href="https://learn.microsoft.com/en-us/nuget/reference/nuget-config-file#packagesources" target="_blank">Configuring the NuGet package sources</a>
* <a href="https://learn.microsoft.com/en-us/nuget/consume-packages/configuring-nuget-behavior#creating-a-new-config-file" target="_blank">Creating a new NuGet config file</a>

## See Also

* [Troubleshooting Common NuGet Setup Issues]({%slug nuget-troubleshooting%})
* [Using the Telerik NuGet Sever as Part of Your CI Workflow]({%slug nuget-keys%})
