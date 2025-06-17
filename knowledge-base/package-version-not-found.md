---
title: Package Version Not Found
description: Learn how to resolve errors like error NU1102 Unable to find package Telerik.UI.for.Maui with version (>= x.x.x).
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

You receive an error similar to:

* `ProjectName depends on Telerik.UI.for.Maui (>= 7.1.0) but Telerik.UI.for.Maui 7.1.0 was not found. An approximate best match of Telerik.UI.for.Maui 6.0.0 was resolved.`

* `error NU1102: Unable to find package Telerik.UI.for.Maui with version (>= 7.1.0)`

## Cause

This error indicates that version `7.1.0` is outside of the subscription period of your license.

## Solution

To solve the issue:

* Use a version of the controls that is covered by your license. The versions covered are those released within the active period of your license.
* Ask the license holder at your company to assign you another license that includes the desired product version.
