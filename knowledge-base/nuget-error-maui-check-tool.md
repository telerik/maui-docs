---
title: A NuGet MAUI Check Tool Error Occurs
page_title: A MAUI Check Tool Remote Source Error Occurs - .NET MAUI Knowledge Base
description: Cannot retrieve information about redth.net.maui.check from a remote source when working with Telerik UI for .NET MAUI.
tags: .net maui, maui, maui check, error, failed
slug: nuget-error-maui-check-tool
type: troubleshooting
ticketid:
res_type: kb
---

## Environment

<table>
	<tbody>
    <tr>
      <td>Product</td>
      <td>Telerik UI for .NET MAUI</td>
    </tr>
  	<tr>
  		<td>Product Version</td>
  		<td>0.0.1</td>
  	</tr>
	</tbody>
</table>

## Description

If you are running the MAUI check tool, you may run into the `Failed to retrieve information about ‘redth.net.maui.check’ from remote source` error.

Also, if you have set up the Telerik NuGet Server as `C:\Program Files\dotnet\sdk\6.0.100-preview.1.21103.13\NuGet.targets(131,5)`, you may run into the `Failed to retrieve information about 'redth.net.maui.check' from remote source 'https://nuget.telerik.com/nuget/FindPackagesById()?id='redth.net.maui.check'&semVerLevel=2.0.0'` error.

## Error Messages

* `Failed to retrieve information about ‘redth.net.maui.check’ from remote source`.
* `Failed to retrieve information about 'redth.net.maui.check' from remote source 'https://nuget.telerik.com/nuget/FindPackagesById()?id='redth.net.maui.check'&semVerLevel=2.0.0'`.

## Cause

The occurred errors indicate that the MAUI-check searches for information in a different NuGet source.

## Solution

You have to disable all NuGet sources and keep the https://api.nuget.org/v3/index.json.

1. Disable an existing source in your NuGet configuration files by running the `dotnet nuget disable source <NAME of the Nuget Source>` command.

1. Update the `maui-check` tool with the `dotnet tool update --global Redth.Net.Maui.Check` command.

3. Run `maui-check`.
