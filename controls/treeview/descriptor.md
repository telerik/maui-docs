---
title: TreeView Descriptor
page_title: .NET MAUI TreeView Documentation - TreeView Descriptor
description: Learn how to define the appearance of the items in the Telerik UI for .NET MAUI TreeView control.
position: 2
slug: treeview-descriptor
---

# .NET MAUI TreeView Descriptor

The Telerik .NET MAUI `TreeViewDescriptor` is part of TreeView items visualization. The `TreeViewDescriptor` defines the data items' hierarchy and how each item is visualized.

The `TreeViewDescriptor` class exposes the following properties described in the table below: 

| Property | Description |
| -------- | ----------- |
| `TargetType` (`System.Type`) | Specifies the type of the data item the descriptor refers to. |
| `IdentityMemberPath` (`string`) | Specifies the path to the identity member of the data item. The identifier member is used to identify the item in the hierarchy. If the property is not specified, the entire item is used instead. |
| `DisplayMemberPath ` (`string`) | Specifies the path to the display member of the data item. The display member is used to visualize the item on the screen. If the property is not specified, the entire item is used instead. |
| `ItemsSourcePath` (`string`) | Specifies the path to the child items source of the data item. |
| `ItemTemplate` (`DataTemplate`) | Specifies the template applied to the respective type of items. |
| `ItemStyle` (`Style` with a target type of `TreeViewItemView`) | Specifies the style of the TreeView items. |

> You can define multiple descriptors in the TreeView.

Here is an example with TreeView descriptor:

**1.** Set up the `RadTreeView` instance:

<snippet id='treeview-getting-started-xaml' />

**2.** Add the `telerik` namespaces:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Create a sample `Item` class:

<snippet id='treeview-getting-started-item' />

**4.** Add the `ViewModel` class:

<snippet id='treeview-getting-started-viewmodel' />

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

## Additional Resources

* [Expand and Collapse TreeView Items]({%slug treeview-expand-collapse%})
* [CheckBoxes in TreeView]({%slug treeview-checkboxes%})
* [Styling the TreeView Item]({%slug treeview-item-style%})
* [Scrolling options]({%slug treeview-scrolling%})
* [Multiple and Single Selection]({%slug treeview-selection%})
* [Events]({%slug treeview-events%})
* [Available Commands in .NET MAUI TreeView]({%slug treeview-commands%})

## See Also

- [.NET MAUI TreeView Product Page](https://www.telerik.com/maui-ui/treeview)
- [.NET MAUI TreeView Forum Page](https://www.telerik.com/forums/maui?tagId=2056)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
