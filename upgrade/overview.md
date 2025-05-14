---
title: Upgrade to a New Version
page_title: Upgrade to a New Version
description: Learn what are the options for upgrading the Telerik UI for .NET MAUI packages to a new version.
slug: upgrade-tutorial
tags: upgrade,tutorial,changes,update
position: 0
---

# Upgrade Your Telerik UI for .NET MAUI Version

This article helps you plan an upgrade to a new version of Telerik UI for .NET MAUI by using the Telerik NuGet server.

## Preparing to Upgrade

Before upgrading the Telerik UI for .NET MAUI version of your project, get acquainted with the release history of the UI components and the breaking changes that may have been introduced:

* <a href="https://www.telerik.com/support/whats-new/maui-ui/release-history" target="_blank">UI for .NET MAUI release history</a>&mdash;Reviewing the release notes for all releases you're planning to go through reveals all changes, fixes, new features, and components that have been implemented.

## Upgrade Using the Telerik NuGet Server

To upgrade the Telerik UI for .NET MAUI components used in your project:

1. Make sure that you have a NuGet feed source with the version you want to upgrade to. This is usually the Telerik NuGet Feed (on [Windows]({%slug maui-getting-started%}) or [MacOS]({%slug maui-getting-started-vs-code%})), but you can also use a local feed from the [MSI installer]({%slug maui-getting-started%}) or [PKG installer]({%slug maui-getting-started-vs-code%}) or [ZIP archive]({%slug installation-approaches %}).

1. Update the version of the `Telerik.UI.for.Maui` package your project references.

## Upgrade Manually Added Assemblies

You can use a [manual installation approach]({%slug installation-approaches%}#manually-using-assembly-references) for referencing the required Telerik UI for .NET MAUI assemblies into your solution. In this case, to upgrade the components to a newer version, you need to replace the assemblies with the assemblies from the latest released version of Telerik .NET MAUI.

## Upgrade from Trial to Commercial License

If you have purchased a license, [download a new license key]({%slug set-up-your-license%}#downloading-the-license-key). This process is referred to as a license key update. Once you have the new license key, use it to [activate the Telerik UI for .NET MAUI]({%slug set-up-your-license%}#activating-the-telerik-ui-for-net-maui-components).

## See Also

- [I Still See the Trial Message after Purchasing a License]({%slug trial-message-commercial-license%})
