---
title: Unable To Load Server Index For Source
description: Learn what are the tips for handling issues related when connecting to the Telerik Nuget Server.
type: troubleshooting
page_title: How to solve error messages like unable o load server index for source
slug: commion-nuget-issues
tags: server index, load, source, nuget, telerik nuget server
res_type: kb
---

| Product | Author | 
| --- | ---- | 
 Telerik UI for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

The most common reasons for issues with the private Telerik NuGet feed are related to:

* Authentication and credentials.
* Licensing. For example, requesting commercial packages with a trial license or vice-versa.
* Missing or wrong local configuration (`NuGet.Config`).
* Network connectivity issues, including **proxies** and **firewalls**.

1. `Unable to load the service index for source https://nuget.telerik.com/v3/index.json` 

This error doesn't indicate the exact cause of the problem. In such cases, check the additional error information which usually provides an error code.

To verify if you can access the Telerik NuGet server and the expected packages, open the <a href="https://nuget.telerik.com/v3/search?q=maui&prerelease=true&skip=0&take=100&semVerLevel=2.0.0" target="_blank">https://nuget.telerik.com/v3/search?q=maui&prerelease=true&skip=0&take=100&semVerLevel=2.0.0</a> URL directly in the web browser and enter your Telerik credentials in the prompt.

As a result, you will see a JSON output with the NuGet packages and versions that are available for you. Depending on your license, search for `Telerik.UI.for.Maui` or `Telerik.UI.for.Maui.Trial`.

If the above URL doesn't open, you have either come across a local networking issue or the NuGet server is down.

2. If the machine (PC or DevOps agent) is behind a proxy.

To check if you're experiencing a networking issue, open the following URL in your web browser:

`https://nuget.telerik.com/v3/search?q=maui`

After you enter your telerik.com `username` and `password`, you should see a JSON search result containing a list of all the `Telerik.UI.for.Maui` packages available to the account you signed in with.
