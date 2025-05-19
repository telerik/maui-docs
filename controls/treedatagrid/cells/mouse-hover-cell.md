---
title: Mouse Hover Cell
page_title: .NET MAUI TreeDataGrid Documentation - Hover Cell
description: Learn how to get the current hovered cell and style the appearance of the cell of the Telerik UI for .NET MAUI TreeDataGrid component.
position: 2
slug: treedatagrid-mouse-hover-cell
---

# .NET MAUI TreeDataGrid Hover Cell

The [Telerik UI for .NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) provides an option to get the data of the cell that the mouse is currently over. In addition, you can change the default hover style. The feature is available only on Desktop&mdash;`WinUI` and `MacCatalyst`.

## Getting the Hovered Cell

The `VisualStateService` property (of type `DataGridVisualStateService`) gets the service that handles visual-state related logic, such as keeping track of the element that the mouse is currently over.

The `DataGridVisualStateService` class encapsulates visual state related logic such as mouse-hovered elements within a `Telerik.Maui.Controls.RadDataGrid` instance. This class exposes the `MouseHoverCell` property (`DataGridCellInfo`) which allows you to get the cell that the mouse is currently over.

Here is an example how to get the hovered cell.

```C#
var hoveredCell = treeDataGrid.VisualStateService.MouseHoverCell;
```

## Styling the Cell

You can specify the style for the cells and rows when the mouse is over by using the `MouseHoverStyle` property (of type `DataGridBorderStyle`) and applying the `BackgroundColor`, `BorderColor`, and `BorderThickness` properties.

> As the TreeDataGrid inherits from the DataGrid, for a runnable example with the Mouse Hover Cell scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **DataGrid > Cells** category.

## See Also

- [Setting the .NET MAUI TreeDataGrid Columns]({%slug treedatagrid-columns-overview%})
- [Sorting .NET MAUI TreeDataGrid Records]({%slug treedatagrid-sorting%})
- [Filtering .NET MAUI TreeDataGrid Records]({%slug treedatagrid-filtering-overview%})