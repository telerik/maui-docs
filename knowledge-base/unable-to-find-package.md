---
title: Unable to Find Package
description: Learn how to sovle the error "`Unable to find package Telerik.UI.for.Maui. No packages exist with this id in source(s) nuget.org`".
type: troubleshooting
page_title: How to solve unable to find package
slug: error-login-failed
tags: server, error missing package, nuget, telerik nuget server
res_type: kb
---

| Author |
| ---- |
| [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |


## Description

When I install the Telerik UI for .NET MAUI NuGet package, I get the following error:

`Unable to find package Telerik.UI.for.Maui. No packages exist with this id in source(s): nuget.org` 

## Cause

The error `Unable to find package in source` indicates that the NuGet package manager searches for the Telerik NuGet package in the wrong package source.

The possible causes are:
* The Telerik NuGet source configuration is missing in the `NuGet.Config` file.
* The NuGet package manager uses an incorrect `NuGet.Config` file. The file may be misplaced or contain incorrect information.

## Solution

1. Inspect the `NuGet.Config` file used by the NuGet package manager.
1. Update the file by following the guidelines for [configuring a NuGet source by using the `NuGet.Config` file]({%slug nuget-config%}).
