---
title: Error 503 Service Unavailable
description: Learn how to solve the "unable to load the server index" and "503 service unavailable" errors for the Telerik Nuget Server. 
type: troubleshooting
page_title: How to solve unable to load the server index and service unavailable
slug: error-service-unavailable
tags: server, error loading package, nuget, telerik nuget server
res_type: kb
---

| Author |
| ---- |
| [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I see the following errors when trying to connect to the Telerik NuGet server (`https://nuget.telerik.com/v3/index.json`).

## Cause 

The errors `Unable to load the service index for source`  and `503 (Service unavailable)` occur when the Telerik NuGet server is temporary unavailable. 

## Solution

Check the state of the Telerik NuGet server at the <a href="https://status.telerik.com/" target="_blank">Telerik live services status page</a> to confirm if the server is affected by any temporary issues.

In urgent cases, download the NuGet packages from the **Downloads** page in your <a href="https://www.telerik.com/account/downloads/" target="_blank">Telerik Account</a> and, as a workaround, [set up a local NuGet repository]({%slug local-nuget-packages%}).
