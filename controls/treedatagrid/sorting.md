---
title: Sorting
page_title: .NET MAUI TreeDataGrid Documentation - Sorting
description: "Learn how to implement the sorting functionality of the Telerik UI for .NET MAUI TreeDataGrid through the UI or by using programmatic sorting over a custom or a defined key which is a property from the model."
position: 10
slug: treedatagrid-sorting
---

# .NET MAUI TreeDataGrid Sorting

The [Telerik UI for .NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) provides a built-in sorting functionality which allows the user to order the view of the presented data and which is available to implement both through the UI and programmatically.

## Sorting through the UI

To sort through the UI, click or tap the column header. `UserSortMode` defines how the user input, such as tapping or clicking the column header, affects the current sort state of the TreeDataGrid.

The `UserSortMode` has the following options: 

* (Default) `Auto`
* `Multiple`
* `None`
* `Single`

You can also enable or disable the sorting of a specific column and define a value which indicates whether the user can sort the data by the column values by using the `CanUserSort` (bool) property.

## Programmatic Sorting

To sort the TreeDataGrid programmatically, use either of the following approaches:

* Sort by a property with the [`PropertySortDescriptor`](#property-sort-descriptor)
* Sort by a custom key with the [`DelegateSortDescriptor`](#delegate-sort-descriptor)

### Sorting by Properties

You can sort the data in a TreeDataGrid by pointing a property from the class that defines your objects. To achieve this scenario, use the `PropertySortDescriptor` and set its `PropertyName` property.

The descriptor exposes the following important properties:

* `PropertyName`&mdash;Gets or sets the name of the property that is used to retrieve the key to sort by.
* `SortOrder`&mdash;Gets or sets the order of the sorting (ascending or descending).

The following snippet shows how to set the `PropertySortDescriptor`.

```XAML
<telerik:RadTreeDataGrid.SortDescriptors>
	<telerik:PropertySortDescriptor PropertyName="Name"/>
</telerik:RadTreeDataGrid.SortDescriptors>
```

Then, define the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

### Sorting by Custom Keys

The difference between the `DelegateSortDescriptor` and the `PropertySortDescriptor` is that the `DelegateSortDescriptor` sorts the data by a custom key, while the `PropertySortDescriptor` sorts the data by a defined key, which is a property from the model.

The `DelegateSortDescriptor` exposes the following properties:

* `KeyLookup`&mdash;Gets or sets the `IKeyLookup` instance that is used to retrieve the sort key for each data item.
* `SortOrder`&mdash;Gets or sets the order of the sorting (ascending or descending).

To use a `DelegateSortDescriptor`, create a class that implements the `IKeyLookup` interface which will return the key by which you want to sort. Then, add the `DelegateSortDescriptor` to the `RadDataGrid.SortDescriptors` collection and set its `KeyLookUp` property.

The following example demonstrates a custom `IKeyLookup` implementation.

```C#
public class CustomIKeyLookup : Telerik.Maui.Controls.Data.IKeyLookup
{
	public object GetKey(object instance)
	{
		return (instance as Item).Name.Length;
	}
}
```

Add it to the `SortDescriptors` collection of the TreeDataGrid:

```C#
this.treeDataGrid.SortDescriptors.Add(new DelegateSortDescriptor() { KeyLookup = new CustomIKeyLookup()});
```

## See Also

- [Setting the Telerik UI for .NET MAUI TreeDataGrid Columns]({%slug treedatagrid-columns-overview%})
- [Filtering .NET MAUI TreeDataGrid Records]({%slug treedatagrid-filtering-overview%})
