---
title: Failed to retrieve information about Telerik.UI.for.Maui from remote source
description: Learn how to solve the error "Failed to retrieve information about 'Telerik.UI.for.Maui' from remote source".
type: troubleshooting
page_title: How to solve failed to retrieve information about Telerik.UI.for.Maui from remote source
slug: failed-retrieve-info-remote-source
tags: server,retrieve information, nuget, telerik nuget server
res_type: kb
---

| Author |
| ---- |
| [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I get the following error when using the Telerik NuGet server:

`Failed to retrieve information about 'Telerik.UI.for.Maui' from remote source 'https://nuget.telerik.com/nuget/FindPackagesById()?id='Telerik.UI.for.Maui'&semVerLevel=2.0.0'.`

## Cause

The error occurs when using the obsolete Telerik NuGet v2 server (`https://nuget.telerik.com/nuget`). As of November 2024, this server is no longer available.

## Solution

Use the Telerik NuGet v3 server. The v3 NuGet server URL is `https://nuget.telerik.com/v3/index.json`.
