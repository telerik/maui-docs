---
title: Binding to Collection
page_title: .NET MAUI DataGrid Documentation - Data Binding
description: Learn how to bind the Telerik .NET MAUI DataGrid to a collection of items and configure the data bindings for its columns.
position: 1
slug: datagrid-data-binding
tags: binding, collection, data, dotnet maui, maui, datagrid, enumerable
---

# .NET MAUI DataGrid Data Binding: Binding to a Collection

This article lists the source types supported by Telerik's .NET MAUI DataGrid. It guides you through the process of binding the DataGrid control to a collection of items and configuring the data binding for its columns.

## Supported Collection Sources

To populate the DataGrid with data, use the `ItemsSource` property of the control. For compatibility reasons, the `ItemsSource` property of the .NET MAUI DataGrid is declared as a `System.Object` type. However, using collections that implement the `IEnumerable` interface is recommended as it gives you more flexibility.

## Binding to an ObservableCollection

When you bind the `RadDataGrid` to a collection that implements the `INotifyCollectionChanged` interface, the DataGrid reflects and displays all changes to that collection, for example, any adding or removing of data items. The .NET MAUI framework implements the `INotifyCollectionChanged` interface in the `ObservableCollection<T>` class.

Implementations of the `System.ComponentModel.ICollection` interface are also fully supported. When using such collection sources, the `RadDataGrid` automatically picks up any group, sort, or filter descriptions defined in the collection and uses them to display the data. This makes the `System.ComponentModel.ICollection` interface implementations the recommended collection source for the DataGrid.

The next example demonstrates how to bind the DataGrid to an `ObservableCollection`. For this example, the DataGrid control is bound to a collection of `Club` objects. Note that the `Club` class inherits from `NotifyPropertyChangedBase`, which is the Telerik implementation of the `INotifyPropertyChanged` interface.

**1.** Define the `Club` class:

<snippet id='datagrid-club-model' />

**2.** Create an `ObservableCollection` in the `ViewModel` class:

<snippet id='datagrid-column-view-model' />

**3.** Bind the collection to the `RadDataGrid` control:

```xaml
<telerik:RadDataGrid x:Name="grid" 
                     ItemsSource="{Binding Clubs}" />
```

**4.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## Binding the Columns

By default, DataGrid will generate typed columns automatically based on the public properties of the underlying data objects. When, for example, you set the `ItemsSource` of the `RadDataGrid` to a collection of clubs (see the sample above), the control will create a separate column for each public property of the `Club` object.

To disable the automatic generation of DataGrid columns and manually define them, set the control's `AutoGenerateColumns` property to `False` and manually populate the `Columns` collection.

**1.** Define the columns:

<snippet id='datagrid-columns-example' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Define the `Club` class:

<snippet id='datagrid-club-model' />

**4.** Create an `ObservableCollection` in the `ViewModel` class:

<snippet id='datagrid-column-view-model' />

> To learn more about defining columns and the different types of columns, you can take a look at the [Columns Section]({%slug datagrid-columns-overview%}).

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
