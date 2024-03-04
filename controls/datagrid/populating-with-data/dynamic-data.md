---
title: Binding to Dynamic Data
page_title: .NET MAUI DataGrid Documentation - Dynamic Data
description: Learn how to bind the Telerik UI for .NET MAUI DataGrid to different types of dynamic data - expando and dynamic objects.
position: 2
slug: datagrid-dynamic-data
tags: binding, dynamic, data, expando, dynamic object, dotnet maui, maui, datagrid
---

# .NET MAUI DataGrid Binding to Dynamic Data

As of the Telerik UI for .NET MAUI 6.8.0 version, the DataGrid supports binding to any type that implements the standard `DLR` interface `IDynamicMetaObjectProvider`, such as `DynamicObject` and `ExpandoObject`

> There are limitations set by Apple which disallows the execution of dynamically generated code. This is explained in the [Mono interpreter on iOS and Mac Catalyst](https://learn.microsoft.com/en-us/dotnet/maui/macios/interpreter?view=net-maui-8.0&source=recommendations) article.
> Because of that app that uses `DynamicObject` or `ExpandoObject` will crash when built in Release for `iOS` and `MacCatalyst`.

The solution to prevent the exception is to use the `MtouchInterpretor` as explained in the [article](https://learn.microsoft.com/en-us/dotnet/maui/macios/interpreter?view=net-maui-8.0&source=recommendations#enable-the-interpreter).

```xml
<PropertyGroup Condition="'$(Configuration)|$(RuntimeIdentifier)'=='Release|maccatalyst-arm64'">
	<MtouchInterpreter>-all,+Telerik.Maui.Controls.Compatibility.dll</MtouchInterpreter>
</PropertyGroup>
```


## Binding to Dynamic Object

> When the bound object is recognized as `IDynamicMetaObjectProvider` type, the DataGrid control uses separate logic that operates with dynamic types. Thus, standard `CLR` properties registered in the dynamic type need to be exposed through the `DLR API`.

The following example shows how to implement `DynamicObject` with dynamic (`DLR`) and static (`CLR`) fields, and data bind it to `RadDataGrid`:

**1.** The following model shows a class that derives from `DynamicObject` and containing one `CLR` property called `Id`. When the DataGrid auto-generates its columns, the `TryGetMember` method of the `DynamicObject` class will be used to fetch the values for each column. 
This said, you will need to implement some logic in the method in order to allow `RadDataGrid` to work with the data - both `CLR` (`Common Language Runtime`) and `DLR` (`Dynamic Language Runtime`).

## Binding to Expando Object



## Additional Resources

- [.NET MAUI DataGrid Product Page](https://www.telerik.com/maui-ui/datagrid)
- [.NET MAUI DataGrid Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Filtering UI in the Telerik UI for .NET MAUI DataGrid]({%slug datagrid-filtering-ui%})
- [Programmatic Filtering in the DataGrid]({%slug datagrid-programmatic-filtering%})
- [Grouping in the DataGrid]({%slug datagrid-grouping-overview%})
- [Styling the Appearance of the DataGrid]({%slug datagrid-styling%})
