---
title: Columns Width
page_title: .NET MAUI TreeDataGrid Documentation - Columns Width
description: Learn what are the options for setting column width to the Telerik TreeDataGrid for .NET MAUI.
position: 4
slug: treedatagrid-columns-width
---

# .NET MAUI TreeDataGrid Columns Width

This article describes how to set a width to the [.NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) column using the `SizeMode` and `Width` properties.

* `SizeMode`(`DataGridColumnSizeMode`)&mdash;Defines the `DataGridColumnSizeMode` value that controls how the column and its associated cells are sized horizontally.
  * `Fixed`&mdash;The column has a fixed width as defined by its Width property.
  * `Stretch`&mdash;The column is stretched to the available width proportionally to its desired width.
  * `Auto`&mdash;The columns is sized to its desired width. That is the maximum desired width of all associated cells.
* `Width`(`double`)&mdash;Specifies the fixed width for the column. Applicable when the `SizeMode` property is set to `DataGridColumnSizeMode`.Fixed.
* `MinimumWidth`(`double`)&mdash;Specifies the minimum width of a column. This property is applicable when setting `SizeMode` column property to `Fixed`. When `MinimumWidth` is set, you can not reduce the width of the column to a value lower than the `MinimumWidth`.
* `ActualWidth` (double): Gets the actual width of the column.

## See Also

- [Setting the Telerik UI for .NET MAUI TreeDataGrid Columns]({%slug treedatagrid-columns-overview%})
- [Filtering .NET MAUI TreeDataGrid Records]({%slug treedatagrid-filtering-overview%})
