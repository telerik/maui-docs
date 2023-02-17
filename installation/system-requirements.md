---
title: System Requirements
page_title: .NET MAUI System Requirements
description: "Learn what system requirements you need to provide when using any of the installation approaches for the Telerik UI for .NET MAUI library."
slug: system-requirements
position: 1
---

# System Requirements for Telerik UI for .NET MAUI

>note Telerik .NET MAUI 3.2.0 supports .NET 7.0.

To develop applications with Telerik UI for .NET MAUI, and depending on the platform you are using, you need to install specific development tools.

* [Prerequisites for Windows](#windows)
* [Prerequisites for macOS](#macos)

## Windows

* Windows 11. Alternatively, Windows 10, version 1809 or later, using [Windows UI Library (WinUI) 3](https://learn.microsoft.com/en-us/windows/apps/winui/winui3/).
* For .NET 7.0 projects, [Visual Studio 2022 Preview](https://visualstudio.microsoft.com/vs/preview/). Otherwise, [Visual Studio 2022 17.3 or later](https://learn.microsoft.com/en-us/dotnet/maui/get-started/installation).

## macOS

While you can develop Android, iOS, and macOS apps on macOS, the operating system does not support WinUI apps.

* macOS 10.15 or later, using [Mac Catalyst](https://developer.apple.com/mac-catalyst/)
* [Xcode](https://developer.apple.com/xcode), latest version
* [Visual Studio 2022 for Mac 17.4 Preview](https://learn.microsoft.com/en-us/dotnet/maui/get-started/installation). The installer will inspect your system and will verify which components are installed and which require an update.
* (For iOS apps) iOS 10 and later

## Supported Platforms

You can use Telerik UI for .NET MAUI for application development for the following mobile operating systems:

| Platform | Supported version |
| ------------- | --------------- |
| Android | 5.0 (API 21) or later |
| iOS | 10 or later |
| macOS | 10.15 or later, using Mac Catalyst |
| Windows | 11 and Windows 10, version 1809 or later, using Windows UI Library (WinUI) 3 |

## See Also

- [First Steps]({%slug maui-getting-started%})
- [Installing from MSI file]({%slug install-msi%})
- [Installing from PKG file]({%slug install-pkg%})
- [Installing with NuGet]({%slug telerik-nuget-server%})
- [Restoring NuGet Packages in Your CI Workflow]({% slug nuget-keys %})
