---
title: .NET MAUI iOS Provisioning Profile Not Found
page_title: .NET MAUI iOS Build Signing Error
description: Could not find any available provisioning profiles on iOS
tags: .net maui, maui, maui check, error, provisioning profile, ios, mac, xcode
slug: ios-maui-provisioning-profile-not-found
---

# Provisioning Profile Not Found when Build .NET MAUI App


If you get this `error: Could not find any available provisioning profiles for HelloMaui on iOS` while trying to build the `Telerik MAUI Demo App` or the `.NET MAUI App` try the following approaches to resolve it:

## First Approach

1. Add your Apple developer account to both **XCode** and **Visual Studio for Mac** from the **Preferences**.

2. Build the App.

## Second approach

1. Create an empty/blank iOS app in XCode and deploy it to a simulator.
 