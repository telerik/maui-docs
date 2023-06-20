---
title: Getting Started
page_title: .NET MAUI DataGrid Documentation - Getting Started
description: "Get started with the Telerik UI for .NET MAUI DataGrid and add the control to your .NET MAUI project."
position: 1
slug: datagrid-getting-started
---

# Getting Started with the .NET MAUI DataGrid

This guide provides the information you need to start using the [Telerik UI for .NET MAUI DataGrid]({% slug datagrid-overview %}) by adding the control to your project.

At the end, you will achieve the following result.

![DataGrid Getting Started](images/datagrid-itemssource.png)

## Prerequisites

Before adding the DataGrid, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

1. When your .NET MAUI application is set up, you are ready to add a DataGrid control to your page.

 ```XAML
<telerik:RadDataGrid x:Name="dataGrid"/>
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

1. Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `CreateMauiApp` method of the `MauiProgram.cs` file of your project:

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

## Visualize Sample Data

The DataGrid provides UI virtualization, so it requires its visual parent to provide vertical or horizontal space for the control to fit into. The following scenarios will measure the DataGrid with infinite width and height constraints and the virtualization will not work:

* Positioning the DataGrid inside a `StackLayout` which is wrapped in a ScrollView.
* Positioning the DataGrid inside a ScrollView.

Now that you have added the control to your view, you need to make sure that is properly loaded with the required data.

By default, the DataGrid will auto-generate rows depending on the number of objects in the collection set as its `ItemsSource`. For demonstration purposes, you will use the following simple business objects:

```C#
public class Data
{
	public string Country { get; set; }
	public string Capital { get; set; }
}
```

After you have created your collection of custom objects, you have to assign it to the `ItemsSource` property of the DataGrid:

```C#
this.dataGrid.ItemsSource = new List<Data>
{
	new Data { Country = "India", Capital = "New Delhi"},
	new Data { Country = "South Africa", Capital = "Cape Town"},
	new Data { Country = "Nigeria", Capital = "Abuja" },
	new Data { Country = "Singapore", Capital = "Singapore" }
};
```


## Additional Resources

- [Setting the .NET MAUI DataGrid Columns]({%slug datagrid-columns-overview%})
- [Grouping in the DataGrid]({%slug datagrid-grouping-overview%})
- [Aggregating Data in the DataGrid]({%slug datagrid-aggregates%})
- [Using the DataGrid Commands]({%slug datagrid-aggregates%})
- [Sorting .NET MAUI DataGrid Records]({%slug datagrid-sorting-overview%})
- [Filtering .NET MAUI DataGrid Records]({%slug datagrid-filtering-overview%})
- [Styling the Appearance of the DataGrid]({%slug datagrid-styling%})

## See Also

- [.NET MAUI DataGrid Product Page](https://www.telerik.com/maui-ui/datagrid)
- [.NET MAUI DataGrid Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
