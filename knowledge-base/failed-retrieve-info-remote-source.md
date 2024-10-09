---
title: Failed to retrieve information about Telerik.UI.for.Maui from remote source
description: Learn what are the tips for retrieving information from remote server.
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

When using the obsolete Telerik NuGet v2 feed after November 2024, this will result in an error:

 `Failed to retrieve information about 'Telerik.UI.for.Maui' from remote source 'https://nuget.telerik.com/nuget/FindPackagesById()?id='Telerik.UI.for.Maui'&semVerLevel=2.0.0'.`

## Solution

The solution is to use the Telerik NuGet v3 feed. The v3 NuGet server URL is `https://nuget.telerik.com/v3/index.json`.