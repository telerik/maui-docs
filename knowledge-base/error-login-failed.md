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

If you're receiving `401 Login Failed` error when connecting to Telerik NuGet Server, you can try to update your NuGet credentials through the Windows Credential Manager. Please follow the steps below:

1. Close all open Visual Studio instances (this is so that all NuGet package manager tasks are stopped).
2. Open the "Credential Manager" app on your PC.
3. Scroll through all the entries until you find any that are for `nuget.telerik.com`.
4. Once you find that entry, expand it and select "edit".
5. Make sure the username and password are the same ones you use for your Telerik account and click
    1. Use the email address in the place of username
    2. Make sure any special characters are escaped (see *Handling Special Characters in Password* below)
    3. Click "Save" 
6. Confirm the URL is correct:
    * The URL to the **v3** server should be HTTPS and appear as `https://nuget.telerik.com/v3/index.json`
    * If you are still using the old **v2** server, make sure the URL does not have a trailing slash. It must be only be `https://nuget.telerik.com/nuget`
7. Reopen Visual Studio and access the Telerik NuGet server. 