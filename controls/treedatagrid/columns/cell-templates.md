---
title: Columns Cell Templates
page_title: .NET MAUI TreeDataGrid  Documentation - Columns Cell Templates
description: Learn how to define cell templates in TreeDataGrid  for .NET MAUI columns.
position: 2
slug: treedatagrid-cell-templates
---

# .NET MAUI TreeDataGrid Columns Cell Templates

This article describes how to extend the functionality of the columns in the [.NET MAUI TelerikDataGrid]({%slug treedatagrid-overview%}) and define custom content and edit templates using the `CellContentTemplate` and `CellEditTemplate` properties.

* `CellContentTemplate` (`DataTemplate`)&mdash;Defines the appearance of each cell associated with the concrete column. `CellContentTemplate` gives you the opportunity to wrap the text inside each DataGrid column. You can add a Label as a content of the Text, Template Column and wrap its text using the Label's `LineBreakMode` property.
* `CellContentTemplateSelector` (`DataTemplateSelector`)&mdash;Defines a `DataTemplateSelector` instance that may be used to retrieve dynamic data templates on a per-cell basis.
* `CellEditTemplate` (`DataTemplate`)&mdash;Defines the editor associated with the concrete column. The `CellEditTemplate` is displayed when the cell is in edit mode.

> As the TreeDataGrid inhertis from the DataGrid, for a runnable example with `CellContentTemplate` and `CellEditTemplate` scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **DataGrid > Columns** category. 

## See Also

- [Column Footers]({%slug treedatagrid-column-footer%})
- [Column Resizing]({%slug treedatagrid-column-resizing%})
- [Columns Width]({%slug treedatagrid-columns-width%})
- [Frozen Columns]({%slug treedatagrid-frozen-columns%})
- [Columns Reordering]({%slug treedatagrid-columns-reordering%})
