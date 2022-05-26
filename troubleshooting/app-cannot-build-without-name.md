---
title: App cannot be built if some RadControls don't have x:Name
page_title: Cannot resolve type error when Telerik UI for .NET MAUI control does not have x:Name 
description: App cannot be built error when there is a Telerik UI for .NE MAUI control without x:Name
type: troubleshooting
page_title: 
slug: app-cannot-build-without-name
---

# App cannot be built if some RadControls don't have x:Name

## Description

You can come across the following error on MacOS, iOS and Windows for some of the controls from the Telerik UI for .NET MAUI suite when added to the page:

"Can't resolve RadDockLayout."

This is the specific error:../MainPage.xaml(3,3): Error XFC0000: Cannot resolve type "http://schemas.telerik.com/2022/xaml/maui:telerik:RadDockLayout". (XFC0000) (MOBLZ_MAUI) XamlC


## Solution

To resolve it, just add x:Name to the RadDockLayout (or any other Telerik .NET MAUI control) definition.