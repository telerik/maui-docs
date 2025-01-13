---
title: Setting Up Your License Key
page_title: Setting Up Your License Key
description: Learn how to activate the Telerik UI for .NET MAUI components by downloading and setting up your Telerik components license key.
slug: set-up-your-license
tags: maui,components,license,activate,download
position: 1
---

# Setting Up Your Telerik UI for .NET MAUI License Key

Starting with the Q1 2025 release, the UI components from the Telerik UI for .NET MAUI library require activation through a license key (trial or commercial). This article describes how to download, install, and update your personal license key.

To install the license key and activate the UI components:

1. [Download the license key](#downloading-the-license-key).

1. [Install or update the license key](#installing-or-updating-your-license-key) on your system or in your project.

> The implementation of the 2025 Telerik UI for .NET MAUI licensing requirements will occur in two phases:
>
> * Phase 1—Starting with the 2025 Q1 release, a missing or invalid license causes [warnings during build]({%slug license-errors-warnings%}). The commercial distributions of the UI components do not exhibit any functional restrictions.
>
> * Phase 2—Starting with the 2025 Q2 release, a missing or invalid license will result in [build errors and run-time indicators]({%slug license-errors-warnings%}), such as watermarks and banners.
>
> Note that future updates of the library may restrict or disable some features when no valid license is present.

## Downloading the License Key

To download a license key for Telerik UI for .NET MAUI, you must have either a developer license or a trial license. If you are new to Telerik UI for .NET MAUI, sign up for a [free trial](https://www.telerik.com/try/ui-for-maui) first, and then follow the steps below.

1. Go to the [License Keys page](https://www.telerik.com/account/your-licenses/license-keys/new) in your Telerik account.

1. Click the **Download License Key** button.

    ![Download a Telerik UI for .NET MAUI License Key](./images/download-license-key.png)

The [Progress Control Panel]({%slug control-panel%}), [automated MSI installer]({%slug automated-installer%}), and the [Visual Studio Extensions]({%slug vs-integration-overview%}) will automatically download and store your license key in your home directory. This makes it available for all projects that you develop on your local machine.

## Installing or Updating Your License Key

Whenever you purchase a new Telerik UI for .NET MAUI license or renew an existing one, always [download](#downloading-the-license-key) and install a new license key. The new license key includes information about all previous license purchases. The procedure for the installation of a new license key and update of a license key is the same:

1. Copy the [downloaded](#downloading-the-license-key) `telerik-license.txt` license key file to your home directory. This makes the license key available to all projects that you develop on your computer:

    * For Windows: `%AppData%\Telerik\telerik.license.txt`
    * For Mac/Linux: `~/.telerik/telerik.license.txt`

    Alternatively, copy the `telerik-license.txt` license key file to the root folder of your project. This makes the license key available only to this project. Do not commit the file to source control as this is your personal license key.

1. Add the `Telerik.Licensing` NuGet package as a project dependency. This package will automatically locate the license file at build time. If your project doesn’t use NuGet packages, see the [next document section](#installing-a-license-key-in-projects-without-nuget-references).

## Installing a License Key in Projects without NuGet References

If you’re not using NuGet packages in your project, add the license as a code snippet:

1. Go to the [License Keys page](https://www.telerik.com/account/your-licenses/license-keys/new) in your Telerik account.

1. On the Telerik UI for .NET MAUI row, click the **View key** link in the **SCRIPT KEY** column.

    ![Download a Telerik UI for .NET MAUI Script Key](./images/download-script-key.png)

1. Copy the C# code snippet into a new file, for example, `TelerikLicense.cs`.

1. Add the `TelerikLicense.cs` file to your project.

>Do not publish the license key code snippet in publicly accessible repositories. This is your personal license key.

## See Also

* [License Activation Errors and Warnings]({%slug license-errors-warnings%})
* [Adding the License Key to CI Services]({%slug add-license-to-ci-cd%})
* [Frequently Asked Questions about Your Telerik UI for .NET MAUI License Key]({%slug licensing-faq%})
