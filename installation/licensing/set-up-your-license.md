---
title: Installing Your License Key
page_title: Setting Up Your License Key
description: Learn how to activate the Telerik UI for .NET MAUI components by downloading and setting up your Telerik components license key.
slug: set-up-your-license
components: ["general"]
tags: maui,components,license,activate,download
position: 1
---

# Installing Your Telerik UI for .NET MAUI License Key

Starting with the Q1 2025 release, the UI components from the Telerik UI for .NET MAUI library require activation through a license key (trial or commercial). This article describes how to download your personal license key and use it to activate the Telerik UI for .NET MAUI components.

An invalid license results in [errors and warnings]({%slug license-errors-warnings%}) during build and run-time indicators such as watermarks and banners.

To download a license key for Telerik UI for .NET MAUI, you must have either a developer license or a trial license. If you are new to Telerik UI for .NET MAUI, [start a free Telerik UI for .NET MAUI trial](https://www.telerik.com/try/ui-for-maui) first, and then follow the steps below.

## Before You Start

* Download your license key from the [License Keys](https://www.telerik.com/account/your-licenses/license-keys) page in your Telerik account.
* If your project uses NuGet packages, install the `Telerik.Licensing` package. This is a required step.
* If Telerik UI for .NET MAUI is referenced in a class library, install `Telerik.Licensing` in the application project that consumes the class library too.
* If the build runs under a service account, CI agent, or another user profile, do not rely on Windows `%AppData%\Telerik` or `C:\Users\[windows_username]\%AppData%\Roaming\Telerik` and on Mac/Linux: `~/.telerik/``%appdata%\Telerik` alone. Use a project-level or environment-based setup instead.

## Choose the Right Installation Approach

Depending on your development environment and preferences, you can install your license key in either of the following ways:

| Scenario | Recommended approach |
|---|---|
| Local development machine with Telerik productivity tools (Telerik.CLI, Progress Control Panel, Visual Studio Extensions, Visual Studio Code Extensions) | Use [automatic installation](#automatic-license-key-installation) |
| Projects with NuGet references | Use [manual installation](#manual-license-key-installation) |
| Projects using assembly references (no NuGet packages) | Use [manual installation](#adding-a-license-key-in-projects-without-nuget-references) |

## Automatic License Key Installation

Telerik provides tools that automatically provision your license key. These tools include the [Progress Control Panel]({%slug control-panel%}), the [Visual Studio Extensions]({%slug vs-integration-overview%}) and [Visual Studio Code extensions]({%slug getting-started-vs-code-integration-overview%}).

<TabStrip>
<TabStripTab title="Telerik.CLI">

To install the license key by using the [Telerik.CLI]({%slug telerik-cli%}):

1. Open the terminal and run the following command to install the Telerik.CLI tool:

```bash
dotnet tool install -g Telerik.CLI --source https://api.nuget.org/v3/index.json
```

2. To download and install the license key, run the following command:

```bash
telerik license get-key
```

</TabStripTab>
<TabStripTab title="VS Extensions">

To install your license key by using the [Telerik UI for .NET MAUI Visual Studio extensions]({%slug vs-integration-overview%}):

1. Open Visual Studio.
1. Go to **Extensions** > **Telerik** **Licensing** > **Download Key**.

    ![.NET MAUI VS Extension License Key](./images/vsx-download-license-key-file.png)

</TabStripTab>
<TabStripTab title="VS Code Extensions">

To install your license key by using the [Telerik UI for .NET MAUI Visual Studio Code extensions menu]({%slug getting-started-vs-code-integration-overview%}):

1. Open Visual Studio Code
1. Open the Visual Studio Code extensions menu:
    * `Ctrl+Shift+P` on Windows/Linux
    * `Cmd+Shift+P` on Mac.

1. Select **Telerik UI for .NET MAUI Template Wizard: Launch** from the menu and press **Enter**. 
1. The **Telerik UI for .NET MAUI Template Wizard** opens.
1. Check the **TELERIK ACCOUNT DETAILS** field in the wizard and press the **Download License Key File** button.

    ![.NET MAUI VS Extension License Key](./images/telerik-vs-code-extension.png)

</TabStripTab>
<TabStripTab title="Progress Control Panel">

To install your Telerik License Key by using the [Progress Control Panel]({%slug control-panel%}), start the application. It automatically downloads your license key file `telerik-license.txt` to your home directory:

* On Windows `%AppData%\Telerik` or `C:\Users\[windows_username]\%AppData%\Roaming\Telerik`.
* On Mac/Linux: `~/.telerik/`.

</TabStripTab>
</TabStrip>

## Manual License Key Installation

To manually download and install a license key for Telerik UI for .NET MAUI:

1. Go to the [License Keys](https://www.telerik.com/account/your-licenses/license-keys) page in your Telerik account.

1. Choose the **Manual Setup** option.

1. Press the **Set Up License Key** button.

1. Press the **Download License Key** button to download the `telerik-license.txt` file.

1. Copy the [downloaded license key file](#manual-license-key-installation) `telerik-license.txt` to your home directory. This makes the license key available to all projects that you develop on your computer:

    * For Windows: `%AppData%\Telerik\telerik-license.txt`. For the standard Windows user, that path resolves to `C:\Users\[windows_username]\AppData\Roaming\Telerik\telerik-license.txt`, it can resolve differently for service accounts.
    * For Mac/Linux: `~/.telerik/telerik-license.txt`. If `.telerik` folder does not exist, create such, and paste the `telerik-license.txt` file in it.
    
Alternatively, copy the `telerik-license.txt` license key file to the root folder of your project. This makes the license key available only to this project. Do not commit the file to source control as this is your personal license key.

When you build the project, the `Telerik.Licensing` NuGet package automatically locates the license file and uses it to activate the MAUI controls.

> If your project doesn’t use NuGet packages, see the [next document section](#adding-a-license-key-in-projects-without-nuget-references).

## Adding a License Key in Projects Without NuGet References

Telerik strongly recommends the use of NuGet packages whenever possible. Only include the license key as a code snippet when NuGet packages are not an option.

If you cannot use NuGet packages in your project, add the license as a code snippet:

1. Go to the [License Keys page](https://www.telerik.com/account/your-licenses/license-keys) in your Telerik account.

1. Press the **View Script Keys** button inside the **Script Keys** column.

1. Choose the **Telerik UI for .NET MAUI** as a product.

1. Copy the C# code snippet into a new file, for example, `TelerikLicense.cs`.

1. Add the `TelerikLicense.cs` file to your project.

>Do not publish the license key code snippet in publicly accessible repositories. This is your personal license key.

## Updating Your License Key

Whenever you purchase a new Telerik UI for .NET MAUI license or renew an existing one, always [download a new license key](#manual-license-key-installation). The new license key includes information about all previous license purchases. This process is referred to as a license key update. Once you have the new license key, use it to [activate the Telerik UI for .NET MAUI](#automatic-license-key-installation).

## See Also

* [License Activation Errors and Warnings]({%slug license-errors-warnings%})
* [Adding the License Key to CI Services]({%slug add-license-to-ci-cd%})
* [Frequently Asked Questions about Your Telerik UI for .NET MAUI License Key]({%slug licensing-faq%})
