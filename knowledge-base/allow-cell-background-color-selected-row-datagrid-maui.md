---
title: Allowing Cell Background Color to Show When Row Is Selected in DataGrid for UI for .NET MAUI on Mac and iOS
description: Learn how to ensure custom cell background colors remain visible when a row is selected in DataGrid for UI for .NET MAUI on iOS and Mac
type: how-to
page_title: Custom Cell Background Color Visibility in Selected Rows in .NET MAUI DataGrid
meta_title: Custom Cell Background Color Visibility in Selected Rows in .NET MAUI DataGrid on iOS and MacCatalyst
slug: allow-cell-background-color-selected-row-datagrid-maui
tags: datagrid, ui-for-net-maui, render-mode, cell-style, row-selection
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | --- | ---- |
| 13.2.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want the cells in the DataGrid to retain their custom background color even when the row is selected. Currently, on iOS and MacCatalyst when a row is selected, the selection style overrides the cell background color, hiding the custom colors. This behavior differs across platforms due to the DataGrid's render mode.

This knowledge base article also answers the following questions:
- How do I make custom cell colors visible in selected rows on iOS and MacCatalyst in .NET MAUI DataGrid?
- Why does the selection style override cell styles on iOS and MacCatalyst in DataGrid for .NET MAUI?
- How can I configure render mode in .NET MAUI DataGrid to show cell styles?

## Solution

To allow cell background colors to remain visible on iOS and MacCatalyst when a row is selected,  set the `RenderMode` property of the `RadDataGrid` to `SkiaSharp`. This ensures that the cell styles are displayed on top of the row selection style.

```csharp
using Telerik.Maui.Controls;

var dataGrid = new RadDataGrid();
dataGrid.RenderMode = RenderMode.SkiaSharp;
```

For additional details about the render mode, refer to the official documentation: [DataGrid Render Mode](https://www.telerik.com/maui-ui/documentation/controls/datagrid/render-mode).

## See Also

- [DataGrid Render Mode](https://www.telerik.com/maui-ui/documentation/controls/datagrid/render-mode)
- [DataGrid Overview](https://www.telerik.com/maui-ui/documentation/controls/datagrid/overview)
