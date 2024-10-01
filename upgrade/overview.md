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

1. Make sure that you have a NuGet feed source with the version you want to upgrade to. This is usually the Telerik NuGet Feed (on [Windows]({%slug maui-getting-started%}) or [MacOS]({%slug maui-getting-started-vs-code%})), but you can also use a local feed from the [MSI installer]({%slug maui-getting-started%}) or [PKG installer]({%slug maui-getting-started-vs-code%}) or [ZIP archive]({%slug download-product-files%}).

1. Update the version of the `Telerik.UI.for.Maui` package your project references. If you are using a trial version, the package name is `Telerik.UI.for.Maui.Trial`.

## Upgrade Manually Added Assemblies

You can use a [manual installation approach]({%slug installation-approaches%}#manually-using-assembly-references) for referencing the required Telerik UI for .NET MAUI assemblies into your solution. In this case, to upgrade the components to a newer version, you need to replace the assemblies with the assemblies from the latest released version of Telerik .NET MAUI.

## Upgrade from Trial to Commercial

If you have purchased a license and you need to migrate from the trial package to the licensed commercial version do the following steps:

* When using assemblies:

1. Make sure you have removed the trial version first.

1. Install the commercial version.

1. Replace the references in the project.

1. Clean the solution.

1. Delete the `bin` and `obj` folders where packages and assemblies may be cached.

1. Re-build your project.

1. Run the application.

* When using the Telerik NuGet Feed:

1. Make sure that you have a NuGet feed source with the version you want to upgrade to. This is usually the Telerik NuGet Feed (on [Windows]({%slug maui-getting-started%}) or [MacOS]({%slug maui-getting-started-vs-code%})), but you can also use a local feed from the [MSI installer]({%slug maui-getting-started%}) or [PKG installer]({%slug maui-getting-started-vs-code%}) or [ZIP archive]({%slug download-product-files%}).

1. Replace the reference to the `Telerik.UI.for.Maui.Trial` package in your project with a reference to the `Telerik.UI.for.Maui` package. If you are referencing other Telerik trial packages that you now have a license for, remove the `.Trial` from the packages names.

1. Clean the solution.

1. Delete the `bin` and `obj` folders where packages and assemblies may be cached.

1. Re-build your project.

1. Run the application.

## See Also

- [I Still See the Trial Message after Purchasing a License]({%slug trial-message-commercial-license%})
