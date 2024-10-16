---
title: Unable To Load Server Index For Source
description: Learn how to handle connectivity issues when using the Telerik Nuget server.
type: troubleshooting
page_title: Unable To Load Server Index For Source
slug: commion-nuget-issues
tags: server index, load, source, nuget, telerik nuget server
res_type: kb
---

| Product | Author | 
| --- | ---- | 
 Telerik UI for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I see the error `Unable to load the service index for source https://nuget.telerik.com/v3/index.json` when trying to connect to the Telerik NuGet server.

## Cause

This error `Unable to load the service index for source https://nuget.telerik.com/v3/index.json` doesn't indicate the exact cause of the problem. In such cases, check the additional error information, which usually provides an error code.

The most common reasons for connectivity issues with the Telerik NuGet server are related to:

* Authentication and credentials.
* Licensing&mdash;for example, requesting commercial packages with a trial license or vice-versa.
* Missing or wrong configuration in the `NuGet.Config` file.
* Network connectivity issues, including proxies and firewalls.

## Solution

* Verify that you can access the Telerik NuGet server and the expected packages: open the <a href="https://nuget.telerik.com/v3/search?q=maui&prerelease=true&skip=0&take=100&semVerLevel=2.0.0" target="_blank">https://nuget.telerik.com/v3/search?q=maui&prerelease=true&skip=0&take=100&semVerLevel=2.0.0</a> URL directly in the web browser and enter your Telerik credentials in the prompt.

  * As a result, you will see a JSON output with the NuGet packages and versions that are available for you. Depending on your license, search for `Telerik.UI.for.Maui` or `Telerik.UI.for.Maui.Trial`.

  * If the above URL doesn't open, you are facing either a network issue or the Telerik NuGet server is temporarily unavailable.

* If the machine (PC or DevOps agent) is behind a proxy or a firewall, implement the required rules so you can access the NuGet server URL above.
