---
title: Selection
page_title: .NET MAUI DataGrid Documentation - Selection
description: "Learn more about how to set the single and multiple selection mode of the Telerik UI for .NET MAUI DataGrid and use the available properties, events, and methods."
position: 7
slug: datagrid-selection-overview
---

# Selection in the .NET MAUI DataGrid

The Telerik UI for .NET MAUI DataGrid exposes a single and multiple selection feature which enables users to select a cell or a row by clicking (tapping) on it.

Users can cancel the selection by clicking the cell or the row again.

To implement the selection feature of the DataGrid, use any of the available properties, methods, and events supported by the DataGrid and depending on your scenario.

## Properties

To modify the selection modes of the DataGrid, use some of its most common properties such as [`SelectionUnit`](#selectionunit) and [`SelectedItems`](#selecteditems). To set the [`SelectionMode`](#selectionmode) property, define which `Unit` can be selected.

### SelectionUnit

The `SelectionUnit` property of type `Telerik.Maui.Controls.Compatibility.DataGrid.DataGridSelectionUnit` allows you to control which `Unit` can be selected:

* (Default) `Row`&mdash;The unit that will be selected is a DataGrid row.
* `Cell`&mdash;The unit that will be selected is a cell within a DataGrid row.

To define a cell when using a selection, utilize the `DataGridCellInfo` class that holds all the information about the cell. To define a row when using a selection, you can use your `data` object.

The example below shows how to set `SelectionUnit` in XAML and code-behind:

```XAML
<telerik:RadDataGrid x:Name="dataGrid"
					 SelectionUnit="Cell" />
```
```C#
var dataGrid = new RadDataGrid();
dataGrid.SelectionUnit = Telerik.Maui.Controls.Compatibility.DataGrid.DataGridSelectionUnit.Cell;
```

### SelectionMode

The `SelectionMode` property of type `Telerik.Maui.Controls.Compatibility.DataGrid.DataGridSelectionMode` provides the following modes:

* (Default) `Single`&mdash;Allows you to select a single unit.
* `Multiple`&mdash;Allows you to select multiple units.
* `None`&mdash;Allows no selection.

The example below shows how to set `SelectionMode` in XAML and code-behind:

```XAML
<telerik:RadDataGrid x:Name="dataGrid"
					 SelectionMode="Multiple" />
```
```C#
var dataGrid = new RadDataGrid();
dataGrid.SelectionMode = Telerik.Maui.Controls.Compatibility.DataGrid.DataGridSelectionMode.Multiple;
```

### SelectedItems

The DataGrid exposes the `SelectedItem` and `SelectedItems` properties which you can use depending on whether you have defined a single or multiple selection mode.

Once you make a selection, you can get or modify the collection with the selected items by using the `SelectedItems` property of type `ObservableCollection` object. It gets or modifies an `ObservableCollection` of the currently selected items. Their type depends on the applied `SelectionUnit`, that is, `DataGridCellInfo` for a cell and a data item for a row. You can also directly listen to the `CollectionChanged` event of the `SelectedItems`.

The `SelectedItem` property gets or sets the value of the selected item in the `DataGrid`. The type of the `SelectedItem` depends on the value of the `SelectedUnit`.

* `Row`&mdash;`SelectedItem` is of type `DataGridCellInfo`.
* `Cell`&mdash;`SelectedItem` is the same type as the business object.

## Events

The DataGrid exposes the `SelectionChanged` event that is triggered whenever the `SelectedItems` collection is changed. The `SelectionChanged` event handler receives the following parameters:

* The sender argument, which is of type object, but can be cast to the `RadDataGrid` type.
* A `DataGridSelectionChangedEventArgs` object, which provides the following properties:
		- `RemovedItems`&mdash;Gets a list of the removed items from the `SelectedItems` collection.
		- `AddedItems`&mdash;Gets a list of the added items to the `SelectedItems` collection.

## Methods

The DataGrid exposes additional functionalities for programmatic selection and deselection of items as methods. They also depend on the applied `SelectionUnit`.

The DataGrid provides the following methods for programmatic selection when the `SelectionUnit` is `Row`:

* `SelectItem`(object item)&mdash;Selects the specified data item and adds it to the `SelectedItems` collection.
* `DeselectItem`(object item)&mdash;Removes the selection for the specified data item and removes it from the `SelectedItems` collection.

The DataGrid provides the following methods for programmatic selection when the `SelectionUnit` is `Cell`:

* `SelectCell`(`DataGridCellInfo` item)&mdash;Selects the DataGrid cell as defined by the specified cell information.
* `DeselectCell`(`DataGridCellInfo` item)&mdash;Removes the selection for the DataGrid cell defined by the specified cell information.

The DataGrid provides the following methods for programmatic selection of all items:

* `SelectAll`()&mdash;Selects all the items as defined when the `SelectionMode` is `Multiple`.
* `DeselectAll`()&mdash;Clears the current selected items as defined by the `SelectionUnit` property.

### Example

The following example shows how to use the methods for programmatic selection exposed by the DataGrid:

1. Add a sample business object:

 <snippet id='datagrid-selection-object'/>

1. Add a `ViewModel` with a list of `Person` objects:

 ```C#
public class ViewModel
{
	public ViewModel()
	{
		this.People = new ObservableCollection<Person>()
		{
			new Person { Name = "Kiko", Age = 23, Department = "Production" },
			new Person { Name = "Jerry", Age = 23, Department = "Accounting and Finance"},
			new Person { Name = "Ethan", Age = 51, Department = "Marketing" },
			new Person { Name = "Isabella", Age = 25, Department = "Marketing" },
			new Person { Name = "Joshua", Age = 45, Department = "Production" },
			new Person { Name = "Logan", Age = 26, Department = "Production"},
			new Person { Name = "Aaron", Age = 32, Department = "Production" },
			new Person { Name = "Elena", Age = 37, Department = "Accounting and Finance"},
			new Person { Name = "Ross", Age = 30, Department = "Marketing" },
		};
	}

	public ObservableCollection<Person> People { get; set; }
}
 ```

1. Add the DataGrid definition:

 ```XAML
<telerik:RadDataGrid x:Name="dataGrid"
					 ItemsSource="{Binding People}" />
 ```

1. Set the `ViewModel` class as a `BindingContext`:

 ```C#
this.BindingContext = new ViewModel();
 ```

1. Now, use various approaches to select the first employee from the Marketing department. Each snippet shows a possible approach:

* In the case of row selection, use the `SelectItem` method:

 ```C#
var firstMarketingItem = ((ObservableCollection<Person>)this.dataGrid.ItemsSource).First(p => p.Department == "Marketing");
this.dataGrid.SelectItem(firstMarketingItem);
 ```

* For a cell selection, use the `SelectCell` method. It takes as a parameter a `DataGridCellInfo` object. The `DataGridCellInfo` object can be easily created by using the needed data item (of type `Person` in this case) and setting the column corresponding to the cell you need to select.

 ```C#
var firstMarketingCell = ((ObservableCollection<Person>)this.dataGrid.ItemsSource).First(p => p.Department == "Marketing");
this.dataGrid.SelectCell(new DataGridCellInfo(firstMarketingCell, this.dataGrid.Columns[2]));
 ```

1. Lastly, call the `SelectAll` or `DeselectAll` method:

 ```C#
this.dataGrid.SelectAll();
 ```

## Additional Resources

- [Grouping in the Telerik UI for .NET MAUI DataGrid]({%slug datagrid-grouping-overview%})
- [Sorting .NET MAUI DataGrid Records]({%slug datagrid-sorting-overview%})
- [Filtering .NET MAUI DataGrid Records]({%slug datagrid-filtering-overview%})

## See Also

- [.NET MAUI DataGrid Product Page](https://www.telerik.com/maui-ui/datagrid)
- [.NET MAUI DataGrid Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
