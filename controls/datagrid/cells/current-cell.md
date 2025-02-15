---
title: Current Cell
page_title: .NET MAUI DataGrid Documentation - Current Cell
description: Learn how to set the behavior and style the appearance of the current cell of the Telerik UI for .NET MAUI DataGrid component.
position: 1
previous_url: /controls/datagrid/current-cell
slug: datagrid-current-cell
---

# .NET MAUI DataGrid Current Cell

 The [Telerik UI for .NET MAUI DataGrid]({%slug datagrid-overview%}) provides options for configuring the behavior and style of its current cell.

## Setting the Behavior

The DataGrid allows you to use the `CurrentCell` property of type `DataGridCellInfo` to programmatically modify the current cell during keyboard navigation, when using the mouse, and so on.

The DataGrid also supports the `CurrentCellChanged` event which is invoked when the current cell changes as a result of user interaction with the keyboard.

The `CurrentCellChanged` event handler receives the following parameters:

* The sender argument, which is of type `object`, but can be cast to the `RadDataGrid` type.
* A `CurrentCellChangedEventArgs` object, which provides the following properties:
	- `OldCurrentCell`&mdash;Gets the previous `CurrentCell`.
	- `NewCurrentCell`&mdash;Gets the new `CurrentCell`.

## Styling the Cell

You can style the current DataGrid cell by using the `CurrentCellStyle` property (of type `Style` with target type `DataGridCurrentCellAppearance`) and applying the `BackgroundColor`, `BorderColor`, and `BorderThickness` properties.

## Example

The following example shows the full implementation of the configurations for the current DataGrid cell.

**1.** Set the `ViewModel`.

<snippet id='datagrid-currentcell-viewmodel' />

**2.** Set the `Person` object.

<snippet id='datagrid-currentcell-dataitem' />

**3.** Provide the DataGrid definition in XAML.

<snippet id='datagrid-currentcell-xaml' />

**4.** Set the style for the `CurrentCellStyle` that is defined in the page'a resources.

<snippet id='datagrid-current-cell-style' />

**5.** Set the `CurrentCellChanged` event.

<snippet id='datagrid-currentcell-changed' />

The following image shows the end result.

![DataGrid Current Cell](../images/datagrid-keyboard-navigation.png)

## Additional Resources

- [.NET MAUI DataGrid Product Page](https://www.telerik.com/maui-ui/datagrid)
- [.NET MAUI DataGrid Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Setting the .NET MAUI DataGrid Columns]({%slug datagrid-columns-overview%})
- [Grouping in the DataGrid]({%slug datagrid-grouping-overview%})
- [Using the DataGrid Commands]({%slug datagrid-aggregates%})
- [Sorting .NET MAUI DataGrid Records]({%slug datagrid-sorting-overview%})
- [Filtering .NET MAUI DataGrid Records]({%slug datagrid-filtering-overview%})