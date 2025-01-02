---
title: Resolving Unauthorized Access Errors during .NET MAUI App Publication
description: Learn how to fix unauthorized access errors when publishing a .NET MAUI app by correctly configuring NuGet package sources.
type: troubleshooting
page_title: How to Fix 401 Unauthorized Errors for NuGet Packages in .NET MAUI App Deployment
slug: unauthorized-access-errors-dotnet-maui
tags: nuget, unauthorized, error, .net maui, publish
res_type: kb
---

## Description

When publishing a .NET MAUI app for the first time, you might encounter errors indicating a failure to retrieve information about various `System.ServiceModel.*` packages from a remote source with a 401 (Unauthorized) response status code. 

This issue arises because Microsoft NuGet packages are being searched for in the Telerik NuGet server instead of the official NuGet repository.

## Environment

| Author |
| ---- |
| [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Cause

The cause of the error is the misconfiguration of the NuGet package sources within the project. The project is incorrectly attempting to retrieve Microsoft NuGet packages from the Telerik NuGet server, where they are not available, leading to unauthorized access errors.

## Solution

To resolve the unauthorized access errors, follow these steps:

1. Open the `.csproj` file of your project.
2. Locate the package references that were being incorrectly searched for in the Telerik server. These references are likely to be `System.ServiceModel.*` packages.
3. If any of these packages have a version specified with a "*" (e.g., `1.0.*`), replace the "*" with the exact version number you wish to use. Using specific versions helps ensure that the correct packages are located and used.
4. Execute the following command in your terminal or command prompt to restore the packages from the official NuGet repository:

```bash
dotnet restore --source https://api.nuget.org/v3/index.json
```

This command forces the `dotnet restore` operation to use the official NuGet package source, ensuring that the correct packages are retrieved and unauthorized access errors are avoided.

## See Also

- [NuGet Package Manager](https://www.nuget.org/)
- [Managing NuGet Packages in Visual Studio](https://docs.microsoft.com/en-us/nuget/consume-packages/package-restore)
- [Configuring NuGet Behavior in Visual Studio](https://docs.microsoft.com/en-us/nuget/consume-packages/configuring-nuget-behavior)
