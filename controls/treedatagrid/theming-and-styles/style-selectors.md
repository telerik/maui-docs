---
title: Style Selectors
page_title: .NET MAUI TreeDataGrid Documentation - Style Selectors
description: Learn how to apply conditional styling to the .NET MAUI TreeDataGrid rows.
position: 3
slug: treedatagrid-style-selectors
---

# .NET MAUI TreeDataGrid Style Selectors

The [.NET MAUI TreeDataGrid]({%slug datagrid-overview%}) component exposes a conditional styling feature. It allows users to apply different styles on a cell or per group header depending on a specific condition.

## Cell Style Selector

You can set a distinct style to a specific cell in a given column based on custom style-selection logic with the following properties:

* `CellContentStyleSelector`(`IStyleSelector`)&mdash;Styles the content of the cell by using the text alignment options (`TextMargin`, `HorizontalTextAlignment`, `VerticalTextAlignment`), the font options (`FontAttributes`, `FontFamily`, `FontSize`) and the `TextColor` property.
* `CellDecorationStyleSelector`(`IStyleSelector`)&mdash;Styles the decoration of a cell.

> For the DataGrid Style Selector example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to the **DataGrid > Styling** category.

## Row Background Style Selector

You can set a different style on a row, an alternate row, and on row details based on custom style-selection logic by using the `RowBackgroundStyleSelector` (`IStyleSelector`) property.
To apply a `RowBackgroundStyleSelector` you have to:
1. Create a custom class that inherits from `IStyleSelector`. 
1. Implement the `SelectStyle` method.

The object item of the `SelectStyle` method is of type `DataGridRowInfo`. The `DataGridRowInfo` represents a class that provides information for each row in DataGrid and exposes the following properties:

* `Item` (`object`)&mdash;Gets the business object associated with the row.
* `IsRowDetails` (`bool`)&mdash;Gets a value that specifies whether the row is a `RowDetail`.
* `IsAlternate` (`bool`)&mdash;Gets a value that specifies whether the row is an alternate one.

## See Also

- [TreeDataGrid Styling]({%slug treedatagrid-styling%})
- [Columns Styling]({%slug treedatagrid-columns-styling%})
