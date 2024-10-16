---
title: Resolving Managed Vtable Types NotSupportedException with Telerik .NET MAUI SkiaSharp controls on Windows
description: Learn how to fix the System.NotSupportedException for managed vtable types in DataGrid for MAUI and other Skia controls by updating the .NET Windows SDK version.
type: troubleshooting
page_title: Fix NotSupportedException for Managed Vtable Types in MAUI DataGrid, BusyIndicator, Gauge and the other Telerik MAUI SkiaSharp controls
slug: datagrid-maui-managed-vtable-types-notsupportedexception
tags: datagrid, maui, notsupportedexception, managed vtable types, skiaSharp
res_type: kb
ticketid: 1667154
---

## Environment

<table>
<tbody>
<tr>
<td>Product</td>
<td>DataGrid for MAUI, <br />
Version 7.1.0</td>
</tr>
</tbody>
</table>

## Description

This article describes how to resolve the following error on Windows: 

```
System.NotSupportedException: Managed vtable types (ie. containing any reference types) are not supported.
```

 which occurs when using any of the Telerik .NET MAUI SkiaSharp controls, such as [DataGrid](https://docs.telerik.com/devtools/maui/controls/datagrid/overview), [BusyIndicator](https://docs.telerik.com/devtools/maui/controls/busyindicator/overview), [Gauge](https://docs.telerik.com/devtools/maui/controls/gauge/overview) and other and: 

*  you've updated Visual Studio 2022 to Version 17.11.5. 
*  you're using the CommunityToolkit and have explicitly set the Windows SDK version in the .csproj file due to its requirement, such as:

```XML
<WindowsSdkPackageVersion>10.0.19041.41</WindowsSdkPackageVersion>
```

## Cause
The exception is related to a known issue in the SkiaSharp library with `WindowsSdkPackageVersion` 10.0.19041.38 and above:

[https://github.com/mono/SkiaSharp/issues/2999](https://github.com/mono/SkiaSharp/issues/2999)

## Solution
To resolve this issue, update the .NET Windows SDK version in your project. Modify the project file (.csproj) to include the following line, which specifies a version of the Windows SDK where the issue has been fixed:

```XML
<WindowsSdkPackageVersion>10.0.19041.54</WindowsSdkPackageVersion>
```

By adding this line to your project file, you ensure that your application uses a version of the Windows SDK that includes the necessary fix for the `NotSupportedException` related to managed vtable types.

## See Also

- [GitHub Issue on SkiaSharp](https://github.com/mono/SkiaSharp/issues/2999)
- [DataGrid Overview](https://docs.telerik.com/devtools/maui/controls/datagrid/overview)
