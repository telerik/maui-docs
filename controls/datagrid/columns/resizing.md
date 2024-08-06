---
title: Column Resizing
page_title: .NET MAUI DataGrid Documentation - Column Resizing
description: Check how to resize the columns in the .NET MAUI DataGrid control
position: 4
slug: datagrid-column-resizing
---

# .NET MAUI DataGrid Column Resizing

Columns inside the [Telerik UI for .NET MAUI DataGrid]({%slug datagrid-overview%}) are resizable by default. The feature is available only on Desktop - `WinUI` and `MacCatalyst`.

On `WinUI` and `MacOS`, you can change the column width by positioning the mouse over the column's vertical grid line (in the column header) and dragging it until the desired size is achieved.

![DataGrid Column Resizing](../images/column-resizing.png)

**Column Resizing on `MacCatalyst`**

![DataGrid Column Resizing](../images/column-resizing-mac.gif)

To resize a column programmatically, you can use the columns `Width` property. For more details review the [Columns Width]({%slug datagrid-columns-width%}) article.

In addition, you can set a `MinimumWidth`(`double`) to the column. This property is applicable when setting `SizeMode` column property to `Fixed`. When `MinimumWidth` is set, you can not reduce the width of the column to a value lower than the `MinimumWidth`. 

## Disabling Resizing

Two ways to disable the resizing.

**1.** Disable the resizing on a DataGrid level 

You can disable the resizing by setting the `CanUserResizeColumns` property to `False`. The default value is `True`.

```XAML
<telerik:RadDataGrid x:Name="grid" 
                     CanUserResizeColumns="False"/>
```

>note When disabling the resizing on a DataGrid level, all the columns won't be resizable.

**2.** Disable the resizing on a column level

To disable the resizing on a specific column, set the `IsResizable` property. The default value is `True`.

```XAML
<telerik:DataGridNumericalColumn PropertyName="StadiumCapacity" 
                                 HeaderText="Stadium Capacity"
                                 IsResizable="False"/>
```

![.NET MAUI DataGrid disable column resizing](../images/column-resizing-disable-column-level.gif)

## Events

The DataGrid control exposes a `ColumnUserResizeCompleted` event that is invoked when the user resizes a column. The `ColumnUserResizeCompleted` event handler receives the following parameters:
* The `sender` argument, which is of type `object`, but can be cast to the `RadDataGrid` type.
* A `ColumnUserResizeCompletedEventArgs` object, which provides the following properties:
	- `Column` (`DataGridColumn`)&mdash;Gets the previously `CurrentCell`.
	- `Width` (`double`)&mdash;Gets the width the Column was resized to.

Here is an example with the `ColumnUserResizeCompleted` event:

**1.** Create a sample model:

<snippet id='datagrid-persondetails' />

**2.** Create a `ViewModel`:

<snippet id='datagrid-reordering-viewmodel' />

**3.** Define the DataGrid in XAML:

<snippet id='datagrid-resizing-example' />

**4.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**5.** The `OnDataGridColumnUserResizeCompleted` implementation:

<snippet id='datagrid-column-resizing-event' />

This is the result:

![.NET MAUI DataGrid Resizing event](../images/datagrid-resizing-event.gif)

## See Also

- [Column Reordering]({%slug datagrid-columns-reordering%})
- [Column Header]({%slug datagrid-column-header%})
- [Column Footer]({%slug datagrid-column-footer%})
