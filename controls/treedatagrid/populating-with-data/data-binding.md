---
title: Binding to Collection
page_title: .NET MAUI TreeDataGrid Documentation - Data Binding
description: Learn how to bind the Telerik .NET MAUI TreeDataGrid to a collection of items and configure the data bindings for its columns.
position: 1
slug: treedatagrid-data-binding
tags: binding, collection, data, dotnet maui, maui, datagrid, enumerable
---

# .NET MAUI TreeDataGrid Data Binding: Binding to a Collection

This article lists the source types supported by the [Telerik UI for .NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}). It guides you through the process of binding the DataGrid control to a collection of items and configuring the data binding for its columns.

## Supported Collection Sources

To populate the DataGrid with data, use the `ItemsSource` property of the control. For compatibility reasons, the `ItemsSource` property of the .NET MAUI DataGrid is declared as a `System.Object` type. However, using collections that implement the `IEnumerable` interface is recommended as it gives you more flexibility.

## Binding to an ObservableCollection

When you bind the `RadTreeDataGrid` to a collection that implements the `INotifyCollectionChanged` interface, the TreeDataGrid reflects and displays all changes to that collection, for example, any adding or removing of data items. The .NET MAUI framework implements the `INotifyCollectionChanged` interface in the `ObservableCollection<T>` class.

Implementations of the `System.ComponentModel.ICollection` interface are also fully supported. When using such collection sources, the `RadTreeDataGrid` automatically picks up any sort, or filter descriptions defined in the collection and uses them to display the data. This makes the `System.ComponentModel.ICollection` interface implementations the recommended collection source for the TreeDataGrid. To display the hierarchy of the items define the [`TreeDataGridItemDescriptor`]({%slug treedatagrid-descriptor%}).

The next example demonstrates how to bind the TreeDataGrid to an `ObservableCollection`. 

For this example, the TreeDataGrid control is bound to a collection of `Data` objects.

**1.** Add a TreeDataGrid control to your page.

```XAML
<telerik:RadTreeDataGrid ItemsSource="{Binding Items}" x:Name="tree"
						 AutoGenerateColumns="False">
	<telerik:RadTreeDataGrid.ItemDescriptors>
		<telerik:TreeDataGridItemDescriptor ChildrenBinding="{Binding Children}" />
	</telerik:RadTreeDataGrid.ItemDescriptors>
	<telerik:RadTreeDataGrid.BindingContext>
		<local:ViewModel />
	</telerik:RadTreeDataGrid.BindingContext>
</telerik:RadTreeDataGrid>
```

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Create a sample `Data` class:

<snippet id='treedatagrid-data-model' />

**4.** Add the `ViewModel` class:

<snippet id='treedatagrid-viewmodel' />

## Binding the Columns

By default, TreeDataGrid generates typed columns automatically based on the public properties of the underlying data objects. When, for example, you set the `ItemsSource` of the `RadTreeDataGrid` to a collection of data (see the sample above), the control will create a separate column for each public property of the `Data` object.

To disable the automatic generation of TreeDataGrid columns and manually define them, set the control's `AutoGenerateColumns` property to `False` and manually populate the `Columns` collection.

**1.** Add a TreeDataGrid control to your page.

<snippet id='treedatagrid-getting-started' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Create a sample `Data` class:

<snippet id='treedatagrid-data-model' />

**4.** Add the `ViewModel` class:

<snippet id='treedatagrid-viewmodel' />

> To learn more about defining columns and the different types of columns, you can take a look at the [Columns Section]({%slug treedatagrid-columns-overview%}).

## Additional Resources

- [.NET MAUI TreeDataGrid Product Page](https://www.telerik.com/maui-ui/treedatagrid)
- [.NET MAUI TreeDataGrid Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Filtering UI in the Telerik UI for .NET MAUI TreeDataGrid]({%slug treedatagrid-filtering-ui%})
- [Programmatic Filtering in the TreeDataGrid]({%slug treedatagrid-programmatic-filtering%})
- [Styling the Appearance of the TreeDataGrid]({%slug treedatagrid-styling%})
