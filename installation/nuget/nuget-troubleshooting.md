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

@[template](/_contentTemplates/common/nuget.md#status-telerik-com)