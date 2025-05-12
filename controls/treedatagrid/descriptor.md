---
title: Item Hierarchy
page_title: .NET MAUI TreeDataGrid Documentation - Item Hierarchy
description: Learn how to define the appearance of the items in the Telerik UI for .NET MAUI TreeDataGrid control.
position: 2
slug: treedatagrid-descriptor
---

# .NET MAUI TreeDataGrid Item Hierarchy

The TreeDataGrid for MAUI exposes `ItemDescriptors` collection (`IList<TreeDataGridItemDescriptor>`). The collection defines the entities that describe an item.
To specify the data items' hierarchy and how each item is visualized, use the `TreeDataGridItemDescriptor` class.

The `TreeDataGridItemDescriptor` class exposes the following properties: 

| Property | Description |
| -------- | ----------- |
| `ChildrenBinding` (`BindingBase`) | Specifies the binding that provides the children of an item in the TreeDataGrid. |
| `ShouldDisplayTreeArrowBinding` (`BindingBase`) | Specifies the binding that checks whether a tree arrow should be displayed for an item that has children. |

> You can define multiple descriptors in the TreeDataGrid.

Here is an example demonstrating how to define the data items' hierarchy by using the TreeDataGrid descriptor:

**1.** Set up the `RadTreeDataGrid` instance:

<snippet id='treedatagrid-getting-started' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Create a sample `Data` class:

<snippet id='treedatagrid-data-model' />

**4.** Add the `ViewModel` class:

<snippet id='treedatagrid-viewmodel' />

**5.** Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `CreateMauiApp` method of the `MauiProgram.cs` file of your project:

```C#
using Telerik.Maui.Controls.Compatibility;

public static class MauiProgram
{
	public static MauiApp CreateMauiApp()
	{
		var builder = MauiApp.CreateBuilder();
		builder
			.UseTelerik()
			.UseMauiApp<App>()
			.ConfigureFonts(fonts =>
			{
				fonts.AddFont("OpenSans-Regular.ttf", "OpenSansRegular");
			});

		return builder.Build();
	}
}
```

> For a runnable example with the TreeDataGrid Descriptor scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **TreeDataGrid > Getting Started** category. 

## See Also

- [.NET MAUI TreeDataGrid Product Page](https://www.telerik.com/maui-ui/treedatagrid)
- [.NET MAUI TreeDataGrid Forum Page](https://www.telerik.com/forums/maui?tagId=2056)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
