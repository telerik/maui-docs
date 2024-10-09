---
title: Package Version Not Found
description: Learn what are the tips for solving erros when the Telerik NuGet package version is not found.
type: troubleshooting
page_title: How to solve erros when the Telerik NuGet package version is not found
slug: package-version-not-found
tags: server, package version not found, nuget, telerik nuget server
res_type: kb
---

| Author |
| ---- |
| [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

If you receive an error similar to:

`ProjectName depends on Telerik.UI.for.Maui (>= 7.1.0) but Telerik.UI.for.Maui 7.1.0 was not found. An approximate best match of Telerik.UI.for.Maui 6.0.0 was resolved.`

or

`error NU1102: Unable to find package Telerik.UI.for.Maui with version (>= 7.1.0)`

This means that version `7.1.0` is outside the subscription period of your license.

## Solution

To solve the issue use the following approaches:
* Use a different version of the controls.
* Ask the license holder at your company to assign you another license that includes the desired product version.
