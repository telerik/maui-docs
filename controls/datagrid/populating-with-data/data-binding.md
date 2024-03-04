---
title: Binding to Collection
page_title: .NET MAUI DataGrid Documentation - Data Binding
description: Learn how to bind the Telerik .NET MAUI DataGrid to a collection of items and configure the data bindings for its columns.
position: 1
slug: datagrid-data-binding
tags: binding, collection, data, dotnet maui, maui, datagrid, enumerable
---

# .NET MAUI DataGrid Configure the Data Bindings

This article lists the types of sources Telerik's .NET MAUI DataGrid can handle and guide you through the process of binding the control to a collection of items and configuring the data bindings for its columns.

## Types of Sources

.NET MAUI DataGrid `ItemsSource` property is declared of type `System.Object` for compatibility reasons but it is recommended to use collections which implement the `IEnumerable` interface.

When bound to a collection which implements the `INotifyCollectionChanged` interface, `RadDataGrid` reflects any changes to this collection (due to add or remove operations, for example) in its UI. In .NET MAUI there is a built-in implementation of this interface – the `ObservableCollection<T>` class.

Implementations of the `System.ComponentModel.ICollection` interface are fully supported as well. Moreover, when such a source is provided, `RadDataGrid` automatically pick up any group/sort/filter descriptions defined on the collection and use those to display the data. With this said, it is recommended to pass in such a collection whenever possible. 

## Binding to an ObservableCollection

For the purposes of this example the control will be bound to a collection of `Club` objects. Please note that the class inherits from `NotifyPropertyChangedBase` which is the Telerik implementation of the `INotifyPropertyChanged` interface.

**1.** Define the `Club` class:

<snippet id='datagrid-club-model' />

**2.** Create an `ObservableCollection` in the `ViewModel` class:

<snippet id='datagrid-column-view-model' />

**3.** Bind this collection to the `RadDataGrid` control:

```xaml
<telerik:RadDataGrid x:Name="grid" 
                     ItemsSource="{Binding Clubs}" />
```

**4.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## Binding the Columns

By default, DataGrid will generate typed columns automatically based on the public properties of the underlying data objects.  When, for example, you set the `ItemsSource` of the `RadDataGrid` to a collection of clubs (see the sample above), the control will create a separate column for each public property of the `Club` object.

If you would like to disable this functionality and manually define the columns yourself, set the control's `AutoGenerateColumns` property to `False` and manually populate the `Columns` collection.

**1.** Define the columns:

<snippet id='datagrid-columns-example' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Use the same `Club` class and `ViewModel` class from the example in the [Binding to an ObservableCollection]({%slug datagrid-data-binding%}#binding-to-an-observablecollection).

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
