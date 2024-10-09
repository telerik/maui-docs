---
title: Unable to Find Package
description: Learn what are the tips for solving unable to find package when using the Telerik Nuget Server.
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

Error `Unable to find package Telerik.UI.for.Maui. No packages exist with this id in source(s): nuget.org` may occur When installing the Telerik NuGet package to the project.

`Unable to find package in source` implies that the Telerik NuGet source is searched in wrong nuget source.

The possible causes for such error message are:
* The Telerik NuGet source configuration is missing in the `NuGet.Config` file.
* The correct `NuGet.Config` file is not used, because the file is missed or misplaced.

## Solution

To specify the correct nuget source, add the Telerik NuGet server to the [NuGet.Config]({%slug nuget-config%}) file.
