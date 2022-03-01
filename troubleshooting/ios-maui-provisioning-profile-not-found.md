---
title: .NET MAUI iOS Provisioning Profile Not Found
page_title: .NET MAUI iOS Build Signing Error
description: "Cannot find any available provisioning profiles on iOS when working with Telerik UI for .NET MAUI."
tags: .net maui, maui, maui check, error, provisioning profile, ios, mac, xcode
slug: ios-maui-provisioning-profile-not-found
---

# The Provisioning Profile Is Not Found When Building the .NET MAUI App

While building the Telerik MAUI Demo App or the .NET MAUI App, you may get the following `Could not find any available provisioning profiles for HelloMaui on iOS` error.

To fix this issue, apply either of the following approaches:

* From the IDE's **Preferences** option, add your Apple developer account to both **XCode** and **Visual Studio for Mac**. Build the application.
* Create an empty or blank iOS application in XCode and deploy it to a simulator.
