---
title: The .NET MAUI iOS Provisioning Profile Is Not Found
page_title: A .NET MAUI iOS Build Signing Error Occurs - .NET MAUI Knowledge Base
description: Cannot find any available provisioning profiles on iOS when working with Telerik UI for .NET MAUI.
tags: .net maui, maui, maui check, error, provisioning profile, ios, mac, xcode
slug: ios-maui-provisioning-profile-not-found
previous_url: /troubleshooting/ios-maui-provisioning-profile-not-found
type: troubleshooting
res_type: kb
---

## Environment

<table>
	<tbody>
    <tr>
      <td>Product</td>
      <td>Progress® Telerik® UI for .NET MAUI</td>
    </tr>
  	<tr>
  		<td>Product Version</td>
  		<td>0.0.1</td>
  	</tr>
	</tbody>
</table>

## Description

While you are building the Telerik MAUI Demo app or the .NET MAUI application, you may get the following `Could not find any available provisioning profiles for HelloMaui on iOS` error.

## Error Message

`Could not find any available provisioning profiles for HelloMaui on iOS`.

## Solution

To achieve the desired scenario, apply either of the following approaches:

* From **Preferences**, add your Apple developer account to both **XCode** and **Visual Studio for Mac**. Build the application.

* Create an empty or blank iOS application in XCode and deploy it to a simulator.
