---
title: Error 401 Login Failed
description: Learn what are the tips for solving error 401 login failed when using the Telerik Nuget Server.
type: troubleshooting
page_title: How to solve 401 error for login failed
slug: error-login-failed
tags: server, login failed error, nuget, telerik nuget server
res_type: kb
---

| Author |
| ---- |
| [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I receive a `401 Login Failed` error when trying to connect to the Telerik NuGet Server.

## Cause

The credentials used by the NuGet package manager are invalid. This may happen after changing the password for your Telerik account.

## Solution

Use the Windows Credential Manager to update your credentials:

1. Close all open Visual Studio instances (this is so that all NuGet package manager tasks are stopped).
2. Open the Windows Credential Manager app on your PC.
3. Locate the entry for `nuget.telerik.com` or `VSCredentials_nuget.telerik.com`, expand it, and select **Edit**.
5. Enter the username and password for your Telerik account and then click **Save**.
    * Use your email address as a username.
    * Escape any special characters.
6. Confirm that the URL is correct: `https://nuget.telerik.com/v3/index.json`.
    
    > If you still use the old v2 NuGet server, make sure the URL does not have a trailing slash: `https://nuget.telerik.com/nuget`.

7. Reopen Visual Studio and access the Telerik NuGet server.
