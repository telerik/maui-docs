---
title: Nuget Maui Check Tool Error
page_title: TMaui Check Tool Remote Source Error
description: Failed to retrieve information about redth.net.maui.check from remote source
slug: nuget-error-maui-check-tool
---

# Nuget Error in Maui Check Tool


If you get this error while running maui-check tool `Failed to retrieve information about ‘redth.net.maui.check’ from remote source`, it means that the maui-check searches for information in a different nuget source. 

and this error if you have Telerik NuGet Server set up: C:\Program Files\dotnet\sdk\6.0.100-preview.1.21103.13\NuGet.targets(131,5): error : Failed to retrieve information about 'redth.net.maui.check' from remote source 'https://nuget.telerik.com/nuget/FindPackagesById()?id='redth.net.maui.check'&semVerLevel=2.0.0'. 

## Solution

You have to disable all nuget sources and keep the https://api.nuget.org/v3/index.json.

1. In order to disable an existing source in your NuGet configuration files: 

`dotnet nuget disable source <NAME of the Nuget Source>`

2. Then update the `maui-check` tool:

`dotnet tool update --global Redth.Net.Maui.Check`

3. Run `maui-check`.
 