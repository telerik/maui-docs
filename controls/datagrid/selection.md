---
title: Selection
page_title: .NET MAUI DataGrid Documentation - Selection
description: Check our &quot;Selection&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 3
slug: datagrid-selection-overview
---

# Selection

The DataGrid exposes a selection feature which enables users to select a cell or a row by clicking (tapping) on it. To cancel the selection, users can click the cell or the row again. The control provides a single and multiple selection feature.

This article explains the basic properties and methods that the DataGrid provides for working with selection.

## Important Properties

The DataGrid supports different selection modes that you can modify through the [SelectionUnit](#selectionunit) and [SelectedItems](#selecteditems) properties. Before you can set the [SelectionMode](#selectionmode), you must choose which `Unit` can be selected.

### SelectionUnit

The `SelectionUnit` property (of type `Telerik.XamarinForms.DataGrid.DataGridSelectionUnit`) allows you to control which `Unit` can be selected:

* (Default) `Row`&mdash;The unit to select is a grid row.
* `Cell`&mdash;The unit to select is a cell within a grid row.

>note To define a cell when using a selection, you can utilize the `DataGridCellInfo` class that holds all the information about the cell. To define a row when using a selection, you can use your `data` object.

The example below shows how to set `SelectionUnit` in XAML and code-behind:

```XAML
<telerik:RadDataGrid x:Name="dataGrid"
					 SelectionUnit="Cell" />
```
```C#
var dataGrid = new RadDataGrid();
dataGrid.SelectionUnit = Telerik.XamarinForms.DataGrid.DataGridSelectionUnit.Cell;
```

### SelectionMode

The `SelectionMode` property (of type `Telerik.XamarinForms.DataGrid.DataGridSelectionMode`) provides the following modes:

* (Default) `Single`&mdash;A single unit may be selected.
* `Multiple`&mdash;Multiple units may be selected.
* `None`&mdash;No selection is allowed.

The example below shows how to set `SelectionMode` in XAML and code-behind:

```XAML
<telerik:RadDataGrid x:Name="dataGrid"
					 SelectionMode="Multiple" />
```
```C#
var dataGrid = new RadDataGrid();
dataGrid.SelectionMode = Telerik.XamarinForms.DataGrid.DataGridSelectionMode.Multiple;
```

### SelectedItems

Once you make a selection, you can get or modify the collection with the selected items by using the `SelectedItems` property of type ObservableCollection&lt;object&gt;. It gets or modifies an `ObservableCollection` of the currently selected items. Their type depends on the applied `SelectionUnit`, that is, `DataGridCellInfo` for a cell and a data item for a row.

>note You can listen to the `CollectionChanged` event of the `SelectedItems` directly.

## Events

- `SelectionChanged`&mdash;An event that is triggered whenever the `SelectedItems` collection is changed. The `SelectionChanged` event handler receives two parameters:
	* The sender argument, which is of type object, but can be cast to the `RadDataGrid` type.
	* A `DataGridSelectionChangedEventArgs` object, which provides the following properties:
		- `RemovedItems`&mdash;Gets a list of the removed items from the `SelectedItems` collection.
		- `AddedItems`&mdash;Gets a list of the added items to the `SelectedItems` collection.

## Methods

Additional functionalities for programmatic selectin and deselection of items are exposed by the DataGrid as methods. They also depend on the applied `SelectionUnit`.

#### Methods for Programmatic Selection When SelectionUnit Is "Row"

* `SelectItem`(object item)&mdash;Selects the specified data item and adds it to the `SelectedItems` collection.
* `DeselectItem`(object item)&mdash;Removes the selection for the specified data item and removes it from the `SelectedItems` collection.

#### Methods for Programmatic Selection When SelectionUnit Is "Cell"

* `SelectCell`(`DataGridCellInfo` item)&mdash;Selects the grid cell as defined by the specified cell information.
* `DeselectCell`(`DataGridCellInfo` item)&mdash;Removes the selection for the grid cell defined by the specified cell information.

#### Methods for Programmatic Selection of All Items

* `SelectAll`()&mdash;Selects all the items as defined when the `SelectionMode` is "Multiple".
* `DeselectAll`()&mdash;Clears the current selected items as defined by the `SelectionUnit` property.

### Example

To illustrate how these methods can be used, let's have the following example:

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

* Lastly, call the `SelectAll` or `DeselectAll` method like this:

 ```C#
this.dataGrid.SelectAll();
 ```

## See Also

* [DataGrid Sorting]({%slug datagrid-sorting-overview%})
* [DataGrid Commands]({%slug datagrid-commands-overview%})
