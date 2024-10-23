---
title: NuGet Package Restore Fails with the Telerik UI for .NET MAUI VS Project Template
page_title: NuGet Package Restores Fails When Installing with the VS Project Template on Windows - .NET MAUI Knowledge Base
description: Learn how to troubleshoot the case when the NuGet package restore fails while trying to run Telerik UI for .NET MAUI with the VS project Template on Windows.
type: troubleshooting
slug: nuget-package-fails
tags: telerik, maui, install, installation, vs, project, template, nuget, package, fail
res_type: kb
---

## Environment

<table>
	<tbody>
    <tr>
      <td>Product</td>
      <td>Progress® Telerik® UI for .NET MAUI</td>
      <td>Telerik® Private NuGet Server</td>
    </tr>
	</tbody>
</table>

## Description

The NuGet package restore failed when I tried to run the Telerik UI for .NET MAUI.

## Cause

The Telerik NuGet Server has not been properly configured.

## Solution

To handle this issue:

1. [Manually add the Telerik NuGet Server as a NuGet package source in Visual Studio]({%slug maui-getting-started %}#prerequisites).
1. Go to the solution in Visual Studio.
1. From the context menu, choose **Restore NuGet Packages**.
1. Clean and rebuild the solution.
