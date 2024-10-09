---
title: Overview
page_title: Telerik NuGet Feed - Telerik UI for .NET MAUI
description: Explore the different ways to add the Telerik NuGet feed to your system, and start using NuGet packages to install the Telerik UI for .NET MAUI components.
tags: maui, dot net maui, microsoft maui, telerik maui, nuget, ui for .net maui controls
slug: telerik-nuget-server
position: 0
previous_url: /telerik-nuget-server, /get-started/install-nuget, /installation/install-nuget, /get-started/windows/first-steps-nuget
---

# NuGet Source

NuGet is a popular .NET package manager. Install the Telerik .NET MAUI controls in your application by adding the Telerik UI for .NET MAUI Nuget feed locally or using the Telerik Private NuGet.

* Set up the remote (online) Telerik NuGet feed in the following ways:

    * [Use Visual Studio]({%slug nuget-server-vs%})
    * [Use the .NET CLI]({%slug nuget-keys%})
    * [Use the Progress Control Panel]({%slug %})
    * [Edit the `Nuget.Config` file]({%slug nuget-config%})

* Set up the local Telerik NuGet feed in the following ways:

    * [Use Visual Studio]({%slug local-nuget-packages%}#setting-up-a-local-telerik-nuget-server-in-visual-studio)
    * [Use `Nuget.Config` file]({%slug local-nuget-packages%}#setting-up-the-nuGet-server-in-nuget.config)

Progress maintains the remote (online) Telerik NuGet Feed for registered users and you can include the Telerik UI for .NET MAUI suite in your project. The benefit of using an online NuGet source is that you will receive notifications for newer component versions and you can update to the latest available version from there.

@[template](/_contentTemplates/common/net-version.md#net-version)

>tip When working with the .NET CLI or editing the `NuGet.Config` manually, you can use your Telerik account credentials or a [NuGet API Key]({%slug nuget-keys%}). If you are logging in to telerik.com through single sign-on (SSO), use a [NuGet API Key]({%slug nuget-keys%}).

>warning Never hard-code Telerik account credentials or NuGet API keys in a `NuGet.Config` file in a GitHub repository, Docker image, or any location that may be accessed by unauthorized parties. A NuGet key is valuable and bad actors can use it to access the NuGet packages that are licensed under your account. A credentials abuse can lead to a review of the affected Telerik account.

## Access NuGet Packages behind Firewall

To access the Telerik NuGet feed behind a firewall that restricts outgoing requests, you may need to allow the following domains:

* `nuget.telerik.com`, which provides authentication and license verification
* `downloads.cdn.telerik.com`, which hosts the NuGet packages

The firewall must allow some of the requests to be redirected from `nuget.telerik.com` to `downloads.cdn.telerik.com`.

## Obsolete Telerik NuGet URL

In addition to the v3 feed URL `https://nuget.telerik.com/v3/index.json`, there is an obsolete NuGet v2 server at `https://nuget.telerik.com/nuget`, which is no longer recommended.

> The NuGet v2 server at `https://nuget.telerik.com/nuget` will be sunset in November 2024.
>
> The new v3 protocol offers faster package searches and restores, improved security, and more reliable infrastructure.
>
> To redirect your feed to the NuGet v3 protocol, all you have to do is to change your NuGet package source URL to `https://nuget.telerik.com/v3/index.json`.

## Troubleshooting

See the [Troubleshooting]({%slug nuget-troubleshooting%}) article for tips about common pitfalls when working with the Telerik NuGet feed.

## See Also

* [System Requirements for Windows]({% slug system-requirements %})
* [Telerik Toolbox for .NET MAUI on Windows]({% slug toolbox-support %})
* [Telerik Extensions and Project Templates for VS on Windows]({% slug visualstudio-extensions %})
* <a href="https://www.telerik.com/maui-ui" target="_blank">Telerik UI for .NET MAUI Product Page</a>