---
title: Using the ZIP Archive
page_title: Using the ZIP Archive
description: This article explains what the ZIP archive with the Telerik UI for .NET MAUI components includes, and how to get it.
slug: zip-archive
tags: manual installation,zip,archive
position: 12
---

# Using the ZIP Archive

The ZIP archive with the Telerik UI for .NET MAUI is another distribution method that helps developers create their own repository with controls. You can store them locally on your system, create a common repo for the developers working on your project, or even build your own private NuGet server with the control versions you need.

Having a downloaded ZIP archive with the controls lets you install them even when you work offline. The archive contains also the Telerik UI for .NET MAUI [sample applications]({%slug sampleapps-overview%}) that you can use for inspiration or learning purposes.

> The most common way to install the Telerik UI for .NET MAUI components is to use the [Telerik NuGet feed]({% slug telerik-nuget-overview %}) or the [automated installer]({%slug automated-installer%}).

## Downloading

To download the ZIP archive with the Telerik UI for .NET MAUI controls:

1. Go to the [Downloads](https://www.telerik.com/account/downloads/product-download?product=MAUI) section of your Telerik account.
1. In the **Installation** section, locate the `Telerik_UI_for_dot_NET_Maui_[version].zip` file and download it.

## Using the ZIP

The `ZIP` archive contains the following folders:

* `Binaries`&mdash;Includes the `Net8` and `Net9` folders. Each folder contains the needed assemblies for Android, iOS, MacCatalyst, and WinUI. You can use them to [manually reference]({%slug assembly-references%}) the Telerik UI for .NET MAUI DLLs in your app.

* `Examples`&mdash;Contains the sample applications demonstrating the Telerik UI for .NET MAUI controls. For more details, go to the [Sample Applications]({%slug sampleapps-overview%}) section.

* `LicenseAgreements`&mdash;Provides the product End-User License Agreement (EULA).

* `Packages`&mdash;Contains the `Telerik.UI.for.Maui.[version].nupkg` NuGet package. Use it in case you need to set up a local NuGet source and reference the `Telerik.UI.for.Maui.[version].nupkg` from there.

## See Also

- [UI for MAUI Installation Methods]({%slug installation-approaches%})
- [Automated Installer]({%slug automated-installer%})
- [Sample Applications]({%slug sampleapps-overview%})
