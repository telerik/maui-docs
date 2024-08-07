---
title: Mouse Hover Cell
page_title: .NET MAUI DataGrid Documentation - Hover Cell
description: Learn how to get the current hovered cell and style the appearance of the cell of the Telerik UI for .NET MAUI DataGrid component.
position: 2
slug: datagrid-mouse-hover-cell
---

# .NET MAUI DataGrid Hover Cell

 The [Telerik UI for .NET MAUI DataGrid]({%slug datagrid-overview%}) provides option to get the data of the cell that the mouse is currently over. In addition, you can change the default hover style. The feature is available only on Desktop - `WinUI` and `MacCatalyst`.

## Getting the Hovered Cell

The DataGrid provides a `VisualStateService` property (of type `DataGridVisualStateService`). This porperty gets the service that handles visual-state related logic, such as keeping track of the element that the mouse is currently over.

The `DataGridVisualStateService` class encapsulates visual state related logic such as mouse-hovered elements within a `Telerik.Maui.Controls.RadDataGrid` instance. This class exposes the `MouseHoverCell` property (`DataGridCellInfo`) which allows you to get the cell that the mouse is currently over.

Here is an example how to get the hovered cell.

```C#
var hoveredCell = dataGrid.VisualStateService.MouseHoverCell;
```

## Styling the Hovered Cell

You can specify the style for the cells and rows when the mouse is over by using the `MouseHoverStyle` property (of type `DataGridBorderStyle`) and applying the `BackgroundColor`, `BorderColor`, and `BorderThickness` properties.

## See Also

- [Setting the .NET MAUI DataGrid Columns]({%slug datagrid-columns-overview%})
- [Grouping in the DataGrid]({%slug datagrid-grouping-overview%})
- [Using the DataGrid Commands]({%slug datagrid-aggregates%})
- [Sorting .NET MAUI DataGrid Records]({%slug datagrid-sorting-overview%})
- [Filtering .NET MAUI DataGrid Records]({%slug datagrid-filtering-overview%})