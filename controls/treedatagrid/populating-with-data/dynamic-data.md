---
title: Binding to Dynamic Data
page_title: .NET MAUI TreeDataGrid Documentation - Dynamic Data
description: Learn how to bind the Telerik UI for .NET MAUI TreeDataGrid to different types of dynamic data - expando and dynamic objects.
position: 2
slug: treedatagrid-dynamic-data
tags: binding, dynamic, data, expando, dynamic object, dotnet maui, maui, datagrid
---

# .NET MAUI TreeDataGrid Data Binding: Binding to Dynamic Data

The [.NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) supports binding to any type that implements the standard `IDynamicMetaObjectProvider` DLR interface, such as `DynamicObject` and `ExpandoObject`.

Using Dynamic Data enables you to filter and sort the data inside the DataGrid both through the UI and programmatically.

## Executing Dynamic Data on iOS and MacCatalyst

When you develop applications for Apple devices and plan to bind the DataGrid to dynamic data, you must consider the <a href = "https://learn.microsoft.com/en-us/dotnet/maui/macios/interpreter?view=net-maui-8.0&source=recommendations" target="_blank">security restrictions set by Apple</a>. These restrictions disallow the execution of dynamically generated code on a device. As a result, apps that use `DynamicObject` or `ExpandoObject` will crash in a release build for iOS and Mac Catalyst with a `System.ExecutionEngineException`.
To prevent the exception, use the `MtouchInterpreter` <a href = "https://learn.microsoft.com/en-us/dotnet/maui/macios/interpreter?view=net-maui-8.0&source=recommendations#enable-the-interpreter" target="_blank"> as recommended by Microsoft</a>.

```xml
<PropertyGroup Condition="'$(Configuration)|$(RuntimeIdentifier)'=='Release|maccatalyst-arm64'">
	<MtouchInterpreter>-all,+Telerik.Maui.Controls.dll</MtouchInterpreter>
</PropertyGroup>
```

For more information about these limitations and the suggested solution, see Microsoft's <a href = "https://learn.microsoft.com/en-us/dotnet/maui/macios/interpreter?view=net-maui-8.0&source=recommendations" target="_blank">Mono interpreter on iOS and Mac Catalyst</a> article.

## Binding to DynamicObject

The following example shows how to implement a `DynamicObject` class with Dynamic Language Runtime (DLR) and Common Language Runtime (CLR) fields and bind it to the TreeDataGrid. The standard CLR properties registered in the dynamic type must be exposed through the DLR API.

The model shows a class that derives from `DynamicObject` and contains a CLR property called `Id`. When the DataGrid auto-generates its columns, the `TryGetMember` method of the `DynamicObject` class will be used to fetch the values for each column. You must also implement a specific logic in the method to allow `RadTreeDataGrid` to work with both CLR and DLR data.

**1.** Add the model for the TreeDataGrid:

<snippet id='treedatagrid-dynamicobject-model' />

**2.** Define the `ViewModel`:

<snippet id='treedatagrid-dynamicobject-viewmodel' />

**3.** Define the `RadTreeDataGrid`:

<snippet id='treedatagrid-dynamicobject' />

**4.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

This is the result:


## Binding to ExpandoObject

**1.** Define the `RadTreeDataGrid` control in XAML:

<snippet id='treedatagrid-expandoobject' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Define the `ViewModel`:

<snippet id='treedatagrid-expandoobject-viewmodel' />

This is the result:


## Additional Resources

- [.NET MAUI TreeDataGrid Product Page](https://www.telerik.com/maui-ui/treedatagrid)
- [.NET MAUI TreeDataGrid Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Filtering UI in the Telerik UI for .NET MAUI TreeDataGrid]({%slug treedatagrid-filtering-ui%})
- [Programmatic Filtering in the TreeDataGrid]({%slug treedatagrid-programmatic-filtering%})
- [Styling the Appearance of the TreeDataGrid]({%slug treedatagrid-styling%})
