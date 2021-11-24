---
title: The .NET MAUI iOS Provisioning Profile Is Not Found
page_title: .NET MAUI Knowledge Base | A .NET MAUI iOS Build Signing Error Occurs
description: "Cannot find any available provisioning profiles on iOS when working with Telerik UI for .NET MAUI."
tags: .net maui, maui, maui check, error, provisioning profile, ios, mac, xcode
slug: ios-maui-provisioning-profile-not-found
type: troubleshooting
ticketid:
publish: false
res_type: kb
---

## Environment

|   |   |
|---|---|
| Product   |Telerik UI for .NET MAUI|
| Product Version | ...  |

## Description

While you are building the Telerik MAUI Demo app or the .NET MAUI application, you may get the following `Could not find any available provisioning profiles for HelloMaui on iOS` error.

## Error Message

`Could not find any available provisioning profiles for HelloMaui on iOS`.

## Solution

Apply either of the following approaches:

* From **Preferenes**, add your Apple developer account to both **XCode** and **Visual Studio for Mac**. Build the application.

* Create an empty or blank iOS application in XCode and deploy it to a simulator.
