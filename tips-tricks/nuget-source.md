---
title: NuGet Source
page_title: Troubleshooting Telerik NuGet Feed Issues
description: Learn how to handle various issues that may occur when you work with the Telerik UI for Blazor library and the NuGet installation approach.
slug: troubleshooting-nuget
tags: telerik, nuget, blazor, ui, troubleshooting, installation
published: True
position: 0
---

# Telerik NuGet Feed Troubleshooting

This article summarizes the issues that may occur when you work with the Telerik UI for .NET MAUI library and the online [Telerik NuGet feed]({%slug %}), and their solutions.

Regardless of the cause for the issue, it is recommended that you start from the section on the commonly occurring issues.

* [Tips for handling common NuGet issues](#tips-for-handling-common-nuget-issues)
* [Removing stored credentials](#removing-saved-credentials)
* [Error `401 Unauthorized`](#error-401-unauthorized)
* [Error `401 Logon failed error`](#error-401-unauthorized)
* [Networking pissues](#networking-problems)
* [Error `Unable to find package`](#unable-to-find-package)
* [Error `503 Service Unavailable`](#error-503-service-unavailable)
* [Message about package `version not found`](#package-version-not-found)
* [Error `Failed to retrieve information about ... from remote source`](#failed-to-retrieve-information-from-remote-source)

@[template](/_contentTemplates/common/nuget.md#status-telerik-com)

## Tips for Handling Common NuGet Issues

The most common reasons for issues with the private Telerik NuGet feed are related to:

* Authentication and credentials.
* Licensing. For example, requesting commercial packages with a trial license or vice-versa.
* Missing or wrong local configuration (`NuGet.Config`).
* Network connectivity issues, including **proxies** and **firewalls**.

Errors like `Unable to load the service index for source https://nuget.telerik.com/v3/index.json` don't indicate the exact cause of the problem. In such cases, check the additional error information which usually provides an error code.

To verify if you can access the Telerik NuGet server and the expected packages, open the <a href="https://nuget.telerik.com/v3/search?q=maui&prerelease=true&skip=0&take=100&semVerLevel=2.0.0" target="_blank">https://nuget.telerik.com/v3/search?q=maui&prerelease=true&skip=0&take=100&semVerLevel=2.0.0</a> URL directly in the web browser and enter your Telerik credentials in the prompt.

As a result, you will see a JSON output with the NuGet packages and versions that are available for you. Depending on your license, search for `Telerik.UI.for.Maui` or `Telerik.UI.for.Maui.Trial`.

If the above URL doesn't open, you have either come across a local networking issue or the NuGet server is down.

## Removing Saved Credentials

If you suspect that your saved credentials are wrong, use the following steps to remove them from Windows and, then, add the correct ones:

1. Remove the saved credentials in the [Windows Credential Manager](https://support.microsoft.com/en-us/windows/accessing-credential-manager-1b5c916a-6a16-889f-8581-fc16e8165ac0). These credentials will appear as `nuget.telerik.com` or `VSCredentials_nuget.telerik.com` entries.
2. Remove the Telerik NuGet package source from Visual Studio.
3. If you have added the Telerik  package source by NuGet CLI, try to remove it from the CLI by running the following commands:
    * [`dotnet nuget list source`](https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet-nuget-list-source)
    * [`dotnet nuget remove source`](https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet-nuget-remove-source)
4. Check if you have any credentials stored in `%AppData%\NuGet\Nuget.Config`. If so, remove them.
5. Try to reset the Visual Studio user data by [forcing NuGet to ask for authentication](https://stackoverflow.com/questions/43550797/how-to-force-nuget-to-ask-for-authentication-when-connecting-to-a-private-feed).
6. Restart Visual Studio.
7. Enter the Telerik NuGet package source again through Visual Studio or CLI. If you are using the feed in a .NET Core application, [store your credentials as plain text](#store-credentials-in-clear-text-for-the-telerik-nuget-feed).

## Error 401 Unauthorized

If your credentials are correct and your license includes the requested product and version, then the password probably contains special characters. You need to escape these characters or the authentication can fail on the NuGet server. For example, a common character you must escape is the ampersand (`&`); however, the character causing the issue may be as unique as the section character (`§`).

To solve the issue:

1. Change the password so that it doesn't include characters you need to escape.
2. Escape the special characters before storing the credentials. For example, `my§uper&P@§§word` encodes to `my&sect;uper&amp;P@&sect;&sect;word`.

Avoid using an online encoder utility for a password. Instead, use a Powershell command:

```Shell
Add-Type -AssemblyName System.Web
[System.Web.HttpUtility]::HtmlEncode('my§uper&P@§§word')
```

Result:

![Powershell Encoding](../../images/nuget-pwd-special-charatcers.png)

## 401 Logon failed error

If you're receiving this error when connecting to Telerik NuGet Server, you can try to update your NuGet credentials through the Windows Credential Manager. Please follow the steps below:

1. Close all open Visual Studio instances (this is so that all NuGet package manager tasks are stopped).
2. Open the "Credential Manager" app on your PC.
3. Scroll through all the entries until you find any that are for nuget.telerik.com.
4. Once you find that entry, expand it and select "edit".
5. Make sure the username and password are the same ones you use for your Telerik account and clisk
    1. Use the email address in the place of username
    2. Make sure any special characters are escaped (see *Handling Special Characters in Password* below)
    3. Click "Save" 
6. Confirm the URL is correct:
    * The URL to the **v3** server should be HTTPS and appear as `https://nuget.telerik.com/v3/index.json`
    * If you are still using the old **v2** server, make sure the URL does not have a trailing slash. It must be only be `https://nuget.telerik.com/nuget`
7. Reopen Visual Studio and access the Telerik NuGet server. 

## Networking Problems

Another common problem is that your machine (PC or DevOps agent) is behind a proxy. To check if you're experiencing a networking issue, open the following URL in your web browser:

`https://nuget.telerik.com/v3/search?q=maui`

After you enter your telerik.com `username` and `password`, you should see a JSON search result containing a list of all the `Telerik.UI.for.Maui` packages available to the account you signed in with.

## Unable to Find Package

If the error occurs for the `Telerik.UI.for.Maui` package, it may look like this:

`error NU1101: Unable to find package Telerik.UI.for.Maui. No packages exist with this id in source(s): nuget.org`

Such an error implies that the [Telerik NuGet source]({%slug %}) is not added or enabled. The possible causes are:

* Missing Telerik NuGet source configuration in the `NuGet.Config` file.
* The correct `NuGet.Config` file is not used, because it is missing or misplaced.

## Error 503 Service Unavailable

If you get a message like `Unable to load the service index for source` and error `503 (Service unavailable`), check the Telerik NuGet server health at the [Telerik live services status page](https://status.telerik.com/).

In urgent cases, download the NuGet packages from your [Telerik Account **Downloads** page](https://www.telerik.com/account/downloads/). Then, [set up a local NuGet feed](https://learn.microsoft.com/en-us/nuget/hosting-packages/local-feeds).

## Package Version Not Found

You may encounter an error similar to:

`ProjectName depends on Telerik.UI.for.Maui (>= 7.1.0) but Telerik.UI.for.Maui 7.1.0 was not found. An approximate best match of Telerik.UI.for.Maui 6.0.0 was resolved.`

or

`error NU1102: Unable to find package Telerik.UI.for.Maui with version (>= 7.1.0)`

This error means that version `7.1.0` is outside the subscription period of your license.

To solve the issue, use a different version or ask the license holder at your company to assign you another license that includes the desired product version.

## Failed to Retrieve Information from Remote Source

An attempt to use the [obsolete Telerik NuGet v2 feed]({%slug installation/nuget%}#obsolete-telerik-nuget-url) after November 2024 will result in an error:

`Failed to retrieve information about 'Telerik.UI.for.Maui' from remote source 'https://nuget.telerik.com/nuget/FindPackagesById()?id='Telerik.UI.for.Blazor'&semVerLevel=2.0.0'.`

The solution is to [use the Telerik NuGet v3 feed]({%slug installation/nuget%}).

Another possible reason for the same error is an incorrect NuGet feed URL.