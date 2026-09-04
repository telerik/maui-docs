---
title: RadDataGrid Rows Missing When Linking or Trimming Is Enabled in .NET MAUI
description: Learn how to resolve an issue where RadDataGrid shows columns but no rows when Link SDKs only, Link All, or .NET MAUI trimming is enabled.
type: troubleshooting
page_title: DataGrid Rows Do Not Appear When Linker or Trimming Is Enabled
slug: datagrid-rows-not-showing-when-linking-enabled
tags: datagrid, maui, linker, trimming, publishTrimmed, link-sdk, link-all, preserve, rows-missing, empty-rows
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 15.0.0 | Telerik UI for .NET MAUI DataGrid | [Desislava Yordanova](https://www.telerik.com/blogs/author/desislava-yordanova) |

## Description

When running an application in Release mode with the linker or IL trimmer enabled (for example, setting the Linker behavior to `Link SDK assemblies only` or `Link all assemblies`, or enabling `<PublishTrimmed>true</PublishTrimmed>` in .NET MAUI), the `RadDataGrid` displays headers and columns normally, but no data rows appear. 

Items exist in the collection bound to `ItemsSource`, but the grid renders zero rows or empty cells. When the linker behavior is changed to `Don't link` / `None`, all rows display as expected.

This knowledge base article also answers the following questions:
- Why does RadDataGrid display columns but no rows in Release mode?
- How to prevent the linker from stripping DataGrid model properties?
- How to configure `[Preserve]` or a linker description file for data models bound to RadDataGrid?

## Cause

The `RadDataGrid` reads data item properties dynamically at runtime using reflection and type descriptors based on the column's `PropertyName` (or auto-generated column definitions).

When the linker or trimmer runs, it strips code that does not have explicit, static references in compiled code. Because the model class properties are accessed dynamically via string property names rather than direct code references, the linker may identify them as unused and remove their getters or constructors. Without these property accessors, the grid's data provider cannot extract the cell values, causing rows to appear empty or not render.

## Solution

To resolve this issue, preserve the data model classes and their members so the linker does not strip them during compilation.

### Approach 1: Use Preserve Attributes on the Data Model

Decorate your model class with the platform-specific `[Preserve]` attribute or the .NET `[DynamicallyAccessedMembers]` attribute:

```csharp
#if IOS || MACCATALYST
[Foundation.Preserve(AllMembers = true)]
#elif ANDROID
[Android.Runtime.Preserve(AllMembers = true)]
#endif
public class Club
{
    public string Name { get; set; }
    public string StadiumCapacity { get; set; }
}
```

Alternatively, use the standard .NET trimming attribute:

```csharp
using System.Diagnostics.CodeAnalysis;

[DynamicallyAccessedMembers(DynamicallyAccessedMemberTypes.All)]
public class Club
{
    public string Name { get; set; }
    public string StadiumCapacity { get; set; }
}
```

### Approach 2: Use a Linker Configuration File (linker.xml)

If you prefer not to add platform-specific attributes to your models, configure a linker descriptor file to preserve all types in your models namespace or assembly.

1. Add an XML file named `linker.xml` to your project root:

```xml
<linker>
  <assembly fullname="YourApp">
    <type fullname="YourApp.Models.*" preserve="all" />
  </assembly>
</linker>
```

2. Include the file in your `.csproj` project configuration:

```xml
<ItemGroup Condition="'$(Configuration)' == 'Release'">
  <TrimmerRootDescriptor Include="linker.xml" />
  <LinkDescription Include="linker.xml" />
</ItemGroup>
```

Rebuild your application in Release mode. The linker will preserve the property accessors, and `RadDataGrid` will display all rows correctly.

## See Also

- [DataGrid Overview]({%slug datagrid-overview%})
- [DataGrid Data Binding]({%slug datagrid-data-binding%})
- [Microsoft Learn: Trimming in .NET MAUI](https://learn.microsoft.com/dotnet/core/deploying/trimming/trim-self-contained)
