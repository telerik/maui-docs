---
title: Crypto Tracker Demo App
page_title: .NET MAUI - Demo Applications
description: "Learn how to download and install the Crypto Tracker Demo App and check out the Telerik UI for .NET MAUI controls library."
slug: maui-crypto-app
tags: .net maui, ui for .net maui, .net maui controls, crypto, tracker, application
position: 3
---

# Crypto Tracker Application

Crypto Tracker demo is a real-case crypto application that shows changes in cryptocurrency prices, built with the Telerik UI for .NET MAUI controls.

![Telerik UI for .NET MAUI CryptoTracker App](../images/crypto-app.png)

You can start using the Crypto Tracker application in the following ways:

You can access the SDKBrowser application in the following ways:

* If you have already installed Telerik UI for .NET MAUI, navigate to the **/[installation-path]/Telerik UI for .NET MAUI [version]/Examples/CryptoTracker** folder and open the `CryptoTracker.sln` file;

* Explore the CryptoTracker code directly in the [MAUI Samples Application repository on GitHub](https://github.com/telerik/maui-samples/tree/main/Samples/CryptoTracker).

>important If you don't have a Telerik UI for .NET MAUI installation, check the [Download Telerik UI for .NET MAUI]({%slug maui-getting-started%}#step-2-download-telerik-ui-for-net-maui%}) and [Install Telerik UI for .NET MAUI]({%slug maui-getting-started%}#step-3-install-telerik-ui-for-net-maui) help topics where all steps are described. 

## Run CryptoTracker on Windows

1. Open the `CryptoTracker.sln` on Windows with Visual Studio 2022.

  ![Telerik UI .NET MAUI CryptoTracker App VS](images/sampleapps-visual-studio.png)

1. Wait for the project to restore.

1. Select the target framework of the project.

  ![Telerik UI .NET MAUI CryptoTracker App](../images/crypto-tracker-visual-studio.png)

1. Select the emulator or device on which you want to run the application.
	
 * CryptoTracker application on Android.

  ![Telerik UI for .NET MAUI CryptoTracker App Android](../images/cryptotracker-android.png)
	
 * CryptoTracker application on WinUI.

  ![Telerik UI for .NET MAUI CryptoTracker App WinUI](../images/cryptotracker-winui.png)

## Run CryptoTracker on macOS

>important Review the [macOS Install .NET MAUI GitHub Wiki page](https://github.com/dotnet/maui/wiki/macOS-Install) for more information how to get started on macOS. 

1. Open Terminal inside the CryptoTracler folder.
1. Run on macOS using the following command:

 `dotnet build -t:Run -f net7.0-maccatalyst`
 
	* CryptoTracker application on MacOS.
	
	![Telerik UI for .NET MAUI CryptoTracker App MacCatalyst](../images/cryptotracker-macos.png)

1. Run on iOS using the following command:

 `dotnet build -t:Run -f net7.0-ios -p:_DeviceName=:v2:udid=02C556DA-64B8-440B-8F06-F8C56BB7CC22`
 
 where the `-p:_DeviceName=:v2:uuid==02C556DA-64B8-440B-8F06-F8C56BB7CC22` is the desired device id.

	* CryptoTracker application on iOS.

	![Telerik UI for .NET MAUI CryptoTracker App iOS](../images/cryptotracker-iphone.png)

