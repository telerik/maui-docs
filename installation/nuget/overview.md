---
title: Overview
page_title: Installing Telerik UI for .NET MAUI with NuGet (Overview)
description: Explore the different ways to add the Telerik NuGet feed to your system and start using NuGet packages to install the Telerik UI for .NET MAUI components.
tags: maui, dot net maui, microsoft maui, telerik maui, nuget, ui for .net maui controls
slug: telerik-nuget-overview
position: 0
previous_url: /telerik-nuget-server, /get-started/install-nuget, /installation/install-nuget
---

# Installing .NET MAUI with NuGet

NuGet is a popular .NET package manager that enables the installation of the Telerik .NET MAUI controls in your application. The NuGet packages are the primary distribution method for the Telerik UI for .NET MAUI controls.

Depending on your development environment, you can choose between two ways to access and download the Telerik UI for .NET MAUI NuGet packages:

* By using the online Telerik NuGet feed.
* By setting up your local repository with downloaded NuGet packages. 

@[template](/_contentTemplates/common/net-version.md#net-version)

## Using the Online Telerik NuGet Feed

Progress maintains an online Telerik NuGet Feed for registered users with an active trial or commercial license. Using the Telerik NuGet server (online NuGet feed) gives you quick access to the latest versions of the Telerik UI for .NET MAUI controls. Furthermore, it helps you keep your application up to date by notifying you about new versions of the controls. 

You can configure your system to use the Telerik NuGet server in the following ways:

  * [By using Visual Studio]({%slug nuget-server-vs%})
  * [By editing the `Nuget.Config` file]({%slug nuget-config%})
  * [By using the Progress Control Panel]({%slug control-panel%})
  * [As part of your CI workflow]({%slug nuget-keys%})

### Accessing NuGet Packages behind a Firewall

Regardless of the method that you use to configure your system for the Telerik NuGet server, you may have to also adjust your firewall rules. To access the Telerik NuGet feed behind a firewall that restricts outgoing requests, allow the following domains:

* `nuget.telerik.com`&mdash;provides authentication and license verification.
* `downloads.cdn.telerik.com`&mdash;hosts the NuGet packages.

The firewall must allow the redirection of requests from `nuget.telerik.com` to `downloads.cdn.telerik.com`.

## Using Locally Available NuGet Packages

Using locally available NuGet packages lets you control the installable versions in your development environment and also enables you to install the Telerik UI for .NET MAUI NuGet packages without internet access.

You can configure your system to use your downloaded NuGet packages in the following ways:

* [By using Visual Studio]({%slug local-nuget-packages%}#setting-up-a-local-telerik-nuget-server-in-visual-studio)
* [By editing the `Nuget.Config` file]({%slug local-nuget-packages%}#setting-up-the-nuGet-server-in-nuget.config)

## See Also

* [Troubleshooting Common NuGet Setup Issues]({%slug nuget-troubleshooting%})
* [System Requirements for Windows]({% slug system-requirements %})
* [Telerik Toolbox for .NET MAUI on Windows]({% slug toolbox-support %})
* [Productivity Extensions for Visual Studio]({% slug vs-integration-overview %})
* <a href="https://www.telerik.com/maui-ui" target="_blank">Telerik UI for .NET MAUI Product Page</a>
