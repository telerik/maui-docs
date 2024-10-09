---
title: Erro 401 Unauthorized
description: Learn what are the tips for handling Error 401 Unauthorized.
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

If you receive `Error 401 Unauthorized` but your credentials are correct and your license includes the requested product and version, then the password contains special characters.

## Solution

You need to escape character from your password like the ampersand (`&`); however, the character causing the issue may be as unique as the section character (`§`).

To solve the issue:

1. Change the password so that it doesn't include characters you need to escape.
2. Escape the special characters before storing the credentials. For example, `my§uper&P@§§word` encodes to `my&sect;uper&amp;P@&sect;&sect;word`.

Avoid using an online encoder utility for a password. Instead, use a PowerShell command:

```Shell
Add-Type -AssemblyName System.Web
[System.Web.HttpUtility]::HtmlEncode('my§uper&P@§§word')
```

Result:

![Powershell Encoding](../images/nuget-pwd-special-charatcers.png)