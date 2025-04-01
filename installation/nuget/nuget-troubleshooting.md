---
title: Troubleshooting
page_title: Troubleshooting Telerik NuGet Feed Issues
description: Learn how to handle various issues that may occur when you work with the Telerik UI for Blazor library and the NuGet installation approach.
slug: nuget-troubleshooting
tags: telerik, nuget, blazor, ui, troubleshooting, installation
published: True
position: 10
---

# Telerik NuGet Feed Troubleshooting

This article summarizes the issues that may occur when you work with the Telerik UI for .NET MAUI library and the online [Telerik NuGet feed]({%slug nuget-keys%}), and their solutions.

The issues listed below are common when upgrading to a new version of Telerik .NET MAUI. Follow the link next to each issue to find the solution. 

* Errors like `Unable to load server index for source` can be related to network connectivity&mdash;The solution is to check the [additional error information and the connection to the Telerik NuGet server]({%slug commion-nuget-issues%}).
* If you suspect that your saved credentials are wrong&mdash;Review the [removing stored credentials]({%slug remove-stored-credentials%}) topic for more details on the steps you need to follow to solve this error.
* [`401 Unauthorized`]({%slug error-unauthorized%})
* [`401 Logon failed error`]({%slug error-login-failed%})
* Error like `Unable to find the Telerik.UI.for.Maui package in nuget.org` occurs when the Telerik NuGet source is searched in wrong NuGet&mdash;Review the [Unable to Find Package]({%slug unable-to-find-package %}) article for more details on this case.
* [Error `503 Service Unavailable`]({%slug error-service-unavailable%})
* Errors like `Unable to find package Telerik.UI.for.Maui with version` and `ProjectName depends on Telerik.UI.for.Maui (>= 7.1.0) but Telerik.UI.for.Maui 7.1.0 was not found` can be related to the subscription period&mdash;Review the [Package Version Not Found]({%slug package-version-not-found%}) article for more details on how to solve this behavior.
* Error `Failed to retrieve information about ... from remote source` occurs when using the v2 server&mdash;The solution is to use the [v3 NuGet feed]({%slug failed-retrieve-info-remote-source%}).

### Quick Access Test (Credentials or Network Access)

You can quickly test your credentials or a specific package search results, the NuGet server is a REST service that can be accessed with a standard web browser. Try the following steps:

1. Open a new **in-private/incognito** browser session/tab.
1. Confirm Credentials
    1. Enter [https://nuget.telerik.com/v3/index.json](https://nuget.telerik.com/v3/index.json) in the address bar and hit Enter.
    1. The web browser will prompt you to login, enter the credentials you want to test. You can test either:
        1. Telerik Account credentials (email address and password)
        1. Telerik NuGet Key (username "api-key", password is the full key value)
    1. You should now see a json result containing the general index listing. This confirms a successful login!
1. Confirm Package Listing
    1. Enter [https://nuget.telerik.com/v3/search?q=telerik.ui.for.maui](https://nuget.telerik.com/v3/search?q=telerik.ui.for.maui) in the address bar and hit Enter.
    1. You should now see a json result containing a list of available packages that match the query.
1. If you want to try again with different credentials (i.e. a different nuget key), close the incognito browser session and open a new one.

@[template](/_contentTemplates/common/nuget.md#status-telerik-com)
