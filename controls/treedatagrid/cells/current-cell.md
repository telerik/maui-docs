---
title: Current Cell
page_title: .NET MAUI TreeDataGrid Documentation - Current Cell
description: Learn how to set the behavior and style the appearance of the current cell of the Telerik UI for .NET MAUI TreeDataGrid component.
position: 1
slug: treedatagrid-current-cell
---

# .NET MAUI TreeDataGrid Current Cell

 The [Telerik UI for .NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) provides options for configuring the behavior and style of its current cell.

## Setting the Behavior

In the TreeDataGrid you can use the `RadDataGrid.CurrentCell` (`DataGridCellInfo` ) property to programmatically modify the current cell during keyboard navigation, when using the mouse, and so on.

By subscribing to the `CurrentCellChanged` event you can listen for the changes in the current cell as a result of user interaction with the keyboard.

The `CurrentCellChanged` event handler receives the following parameters:

* The sender argument, which is of type `object`, but can be cast to the `RadDataGrid` type.
* A `CurrentCellChangedEventArgs` object, which provides the following properties:
	- `OldCurrentCell`&mdash;Gets the previous `CurrentCell`.
	- `NewCurrentCell`&mdash;Gets the new `CurrentCell`.

## Styling the Cell

You can style the current cell by using the `CurrentCellStyle` property (of type `Style` with target type `DataGridCurrentCellAppearance`) and applying the `BackgroundColor`, `BorderColor`, and `BorderThickness` properties.

## Example

As the TreeDataGrid inherits from the DataGrid, for a runnable example with the CurrentCell scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **DataGrid > Keyboard Navigation** category. 

## Additional Resources

- [.NET MAUI TreeDataGrid Product Page](https://www.telerik.com/maui-ui/treedatagrid)
- [.NET MAUI TreeDataGrid Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Setting the .NET MAUI TreeDataGrid Columns]({%slug treedatagrid-columns-overview%})
- [Using the TreeDataGrid Commands]({%slug treedatagrid-aggregates%})
- [Sorting .NET MAUI TreeDataGrid Records]({%slug treedatagrid-sorting%})
- [Filtering .NET MAUI TreeDataGrid Records]({%slug treedatagrid-filtering-overview%})