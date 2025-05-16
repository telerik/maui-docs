---
title: Column Resizing
page_title: .NET MAUI TreeDataGrid Documentation - Column Resizing
description: Learn what are the options to resize the columns in the .NET MAUI TreeDataGrid control.
position: 4
slug: treedatagrid-column-resizing
---

# .NET MAUI TreeDataGrid Column Resizing

Columns inside the [Telerik UI for .NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) are resizable by default. The feature is available only on Desktop&mdash;WinUI and MacCatalyst.

On WinUI and MacOS, you can change the column width by positioning the mouse over the column's vertical grid line (in the column header) and dragging it until the desired size is achieved.

To resize a column programmatically, use the column's `Width` property. For more details, review the [Columns Width]({%slug treedatagrid-columns-width%}) article.

In addition, you can set a `MinimumWidth`(`double`) to the column. This property is applicable when setting `SizeMode` column property to `Fixed`. When `MinimumWidth` is set, you can not reduce the width of the column to a value lower than the `MinimumWidth`. 

## Disabling Resizing

You can disable resizing in two ways.

* Disable the resizing on a TreeDataGrid level&mdash;You can disable the resizing by setting the `CanUserResizeColumns` property to `False`. The default value is `True`.

 ```XAML
 <telerik:RadTreeDataGrid x:Name="grid" 
                          CanUserResizeColumns="False"/>
 ```

  >note When disabling the resizing on a DataGrid level, none of the grid columns will be resizable.


* Disable the resizing on a column level&mdash;To disable the resizing on a specific column, set the `IsResizable` property. The default value is `True`.

 ```XAML
 <telerik:DataGridNumericalColumn PropertyName="StadiumCapacity" 
                                  HeaderText="Stadium Capacity"
                                  IsResizable="False"/>
 ```

## Events

Use the `ColumnUserResizeCompleted` event that is invoked when the user resizes a column. The `ColumnUserResizeCompleted` event handler receives the following parameters:
* The `sender` argument, which is of type `object`, but can be cast to the `RadDataGrid` type.
* A `ColumnUserResizeCompletedEventArgs` object, which provides the following properties:
	- `Column` (`DataGridColumn`)&mdash;Gets the resized column.
	- `Width` (`double`)&mdash;Gets the width the Column was resized to.

## See Also

- [Column Reordering]({%slug treedatagrid-columns-reordering%})
- [Column Header]({%slug treedatagrid-column-header%})
- [Column Footer]({%slug treedatagrid-column-footer%})
