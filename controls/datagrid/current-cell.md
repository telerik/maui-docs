---
title: Current Cell
page_title: .NET MAUI DataGrid Documentation - Current Cell
description: Check the Telerik DataGrid for .NET MAUI Current Cell article.
position: 9
slug: datagrid-current-cell
---

# Current Cell

DataGrid control gives you the option to define the current cell using the `CurrentCell`(of type `DataGridCellInfo`)property. You can modify the current cell programmatically, during a keyboard navigation, using a mouse, etc. 

## Event

The `CurrentCellChanged` event is invoked when the current cell changes during a keyboard navigation. The `CurrentCellChanged` event handler receives two parameters:
	* The sender argument, which is of type object, but can be cast to the `RadDataGrid` type.
	* A `CurrentCellChangedEventArgs` object, which provides the following properties:
		- `OldCurrentCell`&mdash;Gets the previously `CurrentCell`.
		- `NewCurrentCell`&mdash;Gets the new `CurrentCell`.


## Styling

Easily apply a style to the current cell using the `CurrentCellStyle`(of type `DataGridBorderStyle`). Apply `BackgroundColor`, `BorderColor` and `BorderThickness`.

## Example

Here is an example with the `CurrentCell`, `CurrentCellChanged` and `CurrentCellStyle`.

**1** The used ViewModel and Business object:

ViewModel:

<snippet id='datagrid-grouping-propertygroupdescriptor-viewmodel' />

Business object:

<snippet id='datagrid-grouping-propertygroupdescriptor-object' />

**2** DataGrid definition in XAML

<snippet id='datagrid-keyboard-navigation-xaml' />

**3** The style used for the `CurrentCellStyle` and defined in the page's resources: 

<snippet id='datagrid-keyboard-navigation-style' />

**4** The `CurrentCellChanged` event:

<snippet id='datagrid-currentcell-changed' />

This is the final result:

![DataGrid Current Cell](images/datagrid-keyboard-navigation.png)

## See Also

- [Getting Started]({%slug datagrid-getting-started%})
- [Selection]({%slug datagrid-selection-overview%})
- [Sorting]({%slug datagrid-sorting-overview%})
- [Filtering]({%slug datagrid-filtering-overview%})
- [Grouping]({%slug datagrid-grouping-overview%})
- [Editing]({%slug datagrid-editing%})
