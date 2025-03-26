---
title: Error 401 Unauthorized
description: Learn how to resolve issues related to "Error 401 Unauthorized".
type: troubleshooting
page_title: How to solve Error 401 Unauthorized
slug: error-unauthorized
tags: server, error, unauthorized, nuget, telerik nuget server
res_type: kb
---

| Author |
| ---- |
| [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I receive `Error 401 Unauthorized` when trying to connect the Telerik NuGet server. I verified my credentials and they are correct. I also have an active license for the product.

## Cause

If you receive `Error 401 Unauthorized` but your credentials are correct and your license includes the requested product and version, the most probable cause are special characters in the password.

## Solution

Escape the special character in your password, for example, an ampersand (`&`) or a section character (`§`).

To solve the issue, use either of the following methods:

* Change the password so that it doesn't include characters you need to escape.
* Escape the special characters before storing the credentials. For example, `my§uper&P@§§word` encodes to `my&sect;uper&amp;P@&sect;&sect;word`.

Avoid using an online encoder utility for a password. Instead, use a PowerShell command:

```Shell
Add-Type -AssemblyName System.Web
[System.Web.HttpUtility]::HtmlEncode('my§uper&P@§§word')
```

![PowerShell Encoding](../images/nuget-pwd-special-charatcers.png)
