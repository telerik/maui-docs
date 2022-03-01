---
title: NuGet MAUI Check Tool Error
page_title: MAUI Check Tool Remote Source Error
description: "Failed to retrieve information about redth.net.maui.check from a remote source when working with Telerik UI for .NET MAUI."
tags: .net maui, maui, maui check, error, failed
slug: nuget-error-maui-check-tool
---

# Update

Do not use `maui-check` anymore. It was only valid when .NET 6 was in preview. To install MAUI tooling, use `dotnet workload install`.  For example, this command will install all the necessary workloads:

```shell
dotnet workload install maui --ignore-failed-sources
```

# ~~A NuGet Error Occurs in the MAUI Check Tool~~

~~When running the MAUI check tool, you may run into the `Failed to retrieve information about ‘redth.net.maui.check’ from remote source` error.~~

~~If you have set up the Telerik NuGet Server as `C:\Program Files\dotnet\sdk\6.0.100-preview.1.21103.13\NuGet.targets(131,5)`, you may run into the `Failed to retrieve information about 'redth.net.maui.check' from remote source 'https://nuget.telerik.com/nuget/FindPackagesById()?id='redth.net.maui.check'&semVerLevel=2.0.0'`.~~

## Reason

The occurred errors indicate that the MAUI-check searches for information in a different NuGet source.

## ~~Solution~~

~~You have to disable all NuGet sources and keep the https://api.nuget.org/v3/index.json.~~

~~1. Disable an existing source in your NuGet configuration files by running the `dotnet nuget disable source <NAME of the Nuget Source>` command.~~

~~2. Update the `maui-check` tool with the `dotnet tool update --global Redth.Net.Maui.Check` command.~~

~~3. Run `maui-check`.~~
