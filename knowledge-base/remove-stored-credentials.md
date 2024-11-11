---
title: Resetting Stored NuGet Credentials
description: Learn how to change the saved Telerik credentials for the Telerik Nuget server.
type: how-to
page_title: How to Reset Stored Credentials for a NuGet Server
slug: remove-stored-credentials
tags: server, credentials, nuget, telerik nuget server
res_type: kb
---

| Author |
| ---- |
| [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I need to reset and update the credentials used by the NuGet package manager to access the Telerik NuGet server. How can I do that?

This KB also answers the following questions:
* How to reset the saved credentials for the Telerik NuGet server?
* How to remove the stored credentials for the Telerik NuGet server?

## Solution

To update the saved credentials for the NuGet server:

1. Remove the saved credentials in the [Windows Credential Manager](https://support.microsoft.com/en-us/windows/accessing-credential-manager-1b5c916a-6a16-889f-8581-fc16e8165ac0). These credentials will appear as `nuget.telerik.com` or `VSCredentials_nuget.telerik.com` entries.
2. Remove the Telerik NuGet package source from Visual Studio.
3. If you have added the Telerik package source by using the .NET CLI, try to remove it by running the following commands:
    * [`dotnet nuget list source`](https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet-nuget-list-source)
    * [`dotnet nuget remove source`](https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet-nuget-remove-source)
4. Check if you have any credentials stored in `%AppData%\NuGet\Nuget.Config`. If so, remove them.
5. Try to reset the Visual Studio user data by [forcing NuGet to ask for authentication](https://stackoverflow.com/questions/43550797/how-to-force-nuget-to-ask-for-authentication-when-connecting-to-a-private-feed).
6. Restart Visual Studio.
7. Add the Telerik NuGet package source again through Visual Studio or .NET CLI. If you are using the Telerik NuGet feed in a .NET Core application, use a [NuGet API key in the NuGet.Config file]({%slug nuget-config %}).
