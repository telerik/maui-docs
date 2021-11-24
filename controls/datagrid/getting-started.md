---
title: Getting Started
page_title: .NET MAUI DataGrid Documentation | Getting Started
description: "Get started with the Telerik UI for .NET MAUI DataGrid and add the control to your .NET MAUI project."
position: 1
slug: datagrid-getting-started
---

# Getting Started

This guide provides the information you need to start using the Telerik UI for .NET MAUI DataGrid by adding the control to your project.

At the end, you will be able to achieve the following result.

![datagrid-itemssource](images/datagrid-itemssource.png)

## Prerequisites

Before adding the DataGrid, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

## Define the Control

1. When your .NET MAUI application is set up, you are ready to add a DataGrid control to your page.

 ```XAML
<telerikDataGrid:RadDataGrid x:Name="dataGrid"/>
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerikDataGrid="clr-namespace:Telerik.XamarinForms.DataGrid;assembly=Telerik.Maui.Controls.Compatibility"
 ```

1. Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `Configure` method of the `Startup.cs` file of your project:

```C#
using Telerik.Maui.Controls.Compatibility;

public void Configure(IAppHostBuilder appBuilder)
{
	appBuilder		
		.UseTelerik()
		.UseMauiApp<App>();

}
```  

## Visualize Sample Data

The DataGrid provides UI virtualization, so it requires its visual parent to provide vertical or horizontal space for the control to fit into. The following scenarios will measure the DataGrid with infinite width and height constraints and the virtualization will not work:

* Positioning the DataGrid inside a StackLayout which is wrapped in a ScrollView.
* Positioning the DataGrid inside a ScrollView.

1. Now that you have added the control to your view, you need to make sure that is properly loaded with the required data.

  By default, the DataGrid will auto-generate rows depending on the number of objects in the collection set as its `ItemsSource`. For demonstration purposes, you will use the following simple business objects:

 ```C#
public class Data
{
	public string Country { get; set; }
	public string Capital { get; set; }
}
 ```

1. After you have created your collection of custom objects, you have to assign it to the `ItemsSource` property of the DataGrid:

 ```C#
this.dataGrid.ItemsSource = new List<Data>
{
	new Data { Country = "India", Capital = "New Delhi"},
	new Data { Country = "South Africa", Capital = "Cape Town"},
	new Data { Country = "Nigeria", Capital = "Abuja" },
	new Data { Country = "Singapore", Capital = "Singapore" }
};
 ```

## See Also

- [Columns]({%slug datagrid-columns-overview%})
- [Grouping]({%slug datagrid-grouping-overview%})
- [Sorting]({%slug datagrid-sorting-overview%})
