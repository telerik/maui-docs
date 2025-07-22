---
title: Selection
page_title: .NET MAUI TreeDataGrid Documentation - Selection
description: Learn more about how to set the single and multiple selection mode of the Telerik UI for .NET MAUI TreeDataGrid and use the available properties, events, and methods.
position: 12
slug: treedatagrid-selection-overview
---

# Selection in the .NET MAUI TreeDataGrid

The [Telerik UI for .NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) exposes a single and multiple selection feature which enables users to select a cell or a row by clicking (tapping) on it.

Users can cancel the selection by clicking the cell or the row again.

To implement the selection feature of the TreeDataGrid, use any of the available properties, methods, and events supported by the DataGrid and depending on your scenario.

## Properties

To modify the selection modes of the DataGrid, use some of its most common properties such as [`SelectionUnit`](#selectionunit) and [`SelectedItems`](#selecteditems). To set the [`SelectionMode`](#selectionmode) property, define which `Unit` can be selected.

### SelectionUnit

The `SelectionUnit` property of type `Telerik.Maui.Controls.DataGrid.DataGridSelectionUnit` allows you to control which `Unit` can be selected:

* (Default) `Row`&mdash;The unit that will be selected is a DataGrid row.
* `Cell`&mdash;The unit that will be selected is a cell within a DataGrid row.

To define a cell when using a selection, utilize the `DataGridCellInfo` class that holds all the information about the cell. To define a row when using a selection, you can use your `data` object.

The example below shows how to set `SelectionUnit` in XAML and code-behind:

```XAML
<telerik:RadTreeDataGrid x:Name="treeDataGrid"
					     SelectionUnit="Cell" />
```
```C#
var treeDataGrid = new RadTreeDataGrid();
treeDataGrid.SelectionUnit = Telerik.Maui.Controls.DataGrid.DataGridSelectionUnit.Cell;
```

### SelectionMode

The `SelectionMode` property of type `Telerik.Maui.Controls.DataGrid.DataGridSelectionMode` provides the following modes:

* (Default) `Single`&mdash;Allows you to select a single unit.
* `Multiple`&mdash;Allows you to select multiple units.
* `None`&mdash;Allows no selection.

The example below shows how to set `SelectionMode` in XAML and code-behind:

```XAML
<telerik:RadTreeDataGrid x:Name="treeDataGrid"
					     SelectionMode="Multiple" />
```
```C#
var treeDataGrid = new RadTreeDataGrid();
treeDataGrid.SelectionMode = Telerik.Maui.Controls.DataGrid.DataGridSelectionMode.Multiple;
```

### SelectedItems

The TreeDataGrid exposes the `SelectedItem` and `SelectedItems` properties which you can use depending on whether you have defined a single or multiple selection mode.

Once you make a selection, you can get or modify the collection with the selected items by using the `SelectedItems` property of type `ObservableCollection<object>`. It gets or modifies an `ObservableCollection` of the currently selected items. Their type depends on the applied `SelectionUnit`, that is, `DataGridCellInfo` for a cell and a data item for a row. You can also directly listen to the `CollectionChanged` event of the `SelectedItems`.

The `SelectedItem` property gets or sets the value of the selected item in the `DataGrid`. The type of the `SelectedItem` depends on the value of the `SelectedUnit`.

* `Row`&mdash;`SelectedItem` is of type `DataGridCellInfo`.
* `Cell`&mdash;`SelectedItem` is the same type as the business object.

## Events

The TreeDataGrid exposes the `SelectionChanged` event that is triggered whenever the `SelectedItems` collection is changed. The `SelectionChanged` event handler receives the following parameters:

* The sender argument, which is of type object, but can be cast to the `RadDataGrid` type.
* A `DataGridSelectionChangedEventArgs` object, which provides the following properties:
		- `RemovedItems`&mdash;Gets a list of the removed items from the `SelectedItems` collection.
		- `AddedItems`&mdash;Gets a list of the added items to the `SelectedItems` collection.

## Methods

The TreeDataGrid exposes additional functionalities for programmatic selection and deselection of items as methods. They also depend on the applied `SelectionUnit`.

The TreeDataGrid provides the following methods for programmatic selection when the `SelectionUnit` is `Row`:

* `SelectItem`(object item)&mdash;Selects the specified data item and adds it to the `SelectedItems` collection.
* `DeselectItem`(object item)&mdash;Removes the selection for the specified data item and removes it from the `SelectedItems` collection.

The TreeDataGrid provides the following methods for programmatic selection when the `SelectionUnit` is `Cell`:

* `SelectCell`(`DataGridCellInfo` item)&mdash;Selects the DataGrid cell as defined by the specified cell information.
* `DeselectCell`(`DataGridCellInfo` item)&mdash;Removes the selection for the DataGrid cell defined by the specified cell information.

The TreeDataGrid provides the following methods for programmatic selection of all items:

* `SelectAll`()&mdash;Selects all the items as defined when the `SelectionMode` is `Multiple`.
* `DeselectAll`()&mdash;Clears the current selected items as defined by the `SelectionUnit` property.

## Example

Here are examples for using the exposed methods:

* In the case of row selection, use the `SelectItem` method:

```C#
var firstMarketingItem = ((ObservableCollection<Person>)this.treeDataGrid.ItemsSource).First(p => p.Department == "Marketing");
this.treeDataGrid.SelectItem(firstMarketingItem);
```

* For a cell selection, use the `SelectCell` method. It takes as a parameter a `DataGridCellInfo` object. The `DataGridCellInfo` object can be easy created by using the needed data item (of type `Person` in this case) and setting the column corresponding to the cell you need to select.

```C#
var firstMarketingCell = ((ObservableCollection<Person>)this.treeDataGrid.ItemsSource).First(p => p.Department == "Marketing");
this.treeDataGrid.SelectCell(new DataGridCellInfo(firstMarketingCell, this.treeDataGrid.Columns[2]));
```

* Call the `SelectAll` or `DeselectAll` method:

```C#
this.treeDataGrid.SelectAll();
```

## See Also

- [Setting the Telerik UI for .NET MAUI TreeDataGrid Columns]({%slug treedatagrid-columns-overview%})
- [Filtering .NET MAUI TreeDataGrid Records]({%slug treedatagrid-filtering-overview%})
