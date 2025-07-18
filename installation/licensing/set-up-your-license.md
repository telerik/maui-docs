---
title: Setting Up Your License Key
page_title: Setting Up Your License Key
description: Learn how to activate the Telerik UI for .NET MAUI components by downloading and setting up your Telerik components license key.
slug: set-up-your-license
tags: maui,components,license,activate,download
position: 1
---

# Setting Up Your Telerik UI for .NET MAUI License Key

Starting with the Q1 2025 release, the UI components from the Telerik UI for .NET MAUI library require activation through a license key (trial or commercial). This article describes how to download your personal license key and use it to activate the Telerik UI for .NET MAUI components.

An invalid license results in [errors and warnings]({%slug license-errors-warnings%}) during build and run-time indicators such as watermarks and banners.

## Downloading the License Key

To download a license key for Telerik UI for .NET MAUI, you must have either a developer license or a trial license. If you are new to Telerik UI for .NET MAUI, sign up for a [free trial](https://www.telerik.com/try/ui-for-maui) first, and then follow the steps below.

1. Go to the [License Keys](https://www.telerik.com/account/your-licenses/license-keys) page in your Telerik account.

1. Click the **Download License Key** button.

    ![Download a Telerik UI for .NET MAUI License Key](./images/download-license-key.png)

The [Progress Control Panel]({%slug control-panel%}), [automated installers]({%slug automated-installer%}), and the [Visual Studio Extensions]({%slug vs-integration-overview%}) will automatically download and store your license key in your home directory. This makes it available for all projects that you develop on your local machine.

## Activating the Telerik UI for .NET MAUI Components

To activate the Telerik UI for .NET MAUI controls:

* Copy the [downloaded](#downloading-the-license-key) `telerik-license.txt` license key file to your home directory. This makes the license key available to all projects that you develop on your computer:

    * For Windows: `%AppData%\Telerik\telerik-license.txt`.
        * For the standard Windows user, that path resolves to `C:\Users\[windows_username]\AppData\Roaming\Telerik\telerik-license.txt`, it can resolve differently for service accounts.
    * For Mac/Linux: `~/.telerik/telerik-license.txt`. If `.telerik` folder does not exist, create such, and paste the `telerik-license.txt` file in it.
    
* Alternatively, copy the `telerik-license.txt` license key file to the root folder of your project. This makes the license key available only to this project. Do not commit the file to source control as this is your personal license key.

When you build the project, the `Telerik.Licensing` NuGet package automatically locates the license file and uses it to activate the MAUI controls.

> If your project doesn’t use NuGet packages, see the [next document section](#installing-a-license-key-in-projects-without-nuget-references).

## Installing a License Key in Projects without NuGet References

Telerik strongly recommends the use of NuGet packages whenever possible. Only include the license key as a code snippet when NuGet packages are not an option.

If you cannot use NuGet packages in your project, add the license as a code snippet:

1. Go to the [License Keys page](https://www.telerik.com/account/your-licenses/license-keys) in your Telerik account.

1. On the Telerik UI for .NET MAUI row, click the **View key** link in the **SCRIPT KEY** column.

    ![Download a Telerik UI for .NET MAUI Script Key](./images/download-script-key.png)

1. Copy the C# code snippet into a new file, for example, `TelerikLicense.cs`.

1. Add the `TelerikLicense.cs` file to your project.

>Do not publish the license key code snippet in publicly accessible repositories. This is your personal license key.

## Updating Your License Key

Whenever you purchase a new Telerik UI for .NET MAUI license or renew an existing one, always [download a new license key](#downloading-the-license-key). The new license key includes information about all previous license purchases. This process is referred to as a license key update. Once you have the new license key, use it to [activate the Telerik UI for .NET MAUI](#activating-the-telerik-ui-for-net-maui-components).

## See Also

* [License Activation Errors and Warnings]({%slug license-errors-warnings%})
* [Adding the License Key to CI Services]({%slug add-license-to-ci-cd%})
* [Frequently Asked Questions about Your Telerik UI for .NET MAUI License Key]({%slug licensing-faq%})
