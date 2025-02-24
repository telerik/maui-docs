---
title: Changing Background Color of Rows and Columns in DataGrid for MAUI
description: Learn how to customize the background color of rows and columns in the DataGrid for MAUI component.
type: how-to
page_title: How to Customize Background Color in DataGrid Rows and Columns for MAUI
slug: datagrid-maui-change-background-color
tags: datagrid, maui, background, color, row, column
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.0.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description
Changing the background color of DataGrid rows or columns is essential for enhancing the visual appearance of the grid or highlighting specific data. 

This knowledge base article also answers the following questions:
- How can I style the rows in a DataGrid for MAUI?
- What property allows changing the column background color in DataGrid for MAUI?
- How do I apply custom styling to DataGrid cells in MAUI?

## Solution

To customize the background color of columns in the DataGrid for MAUI, utilize the `CellDecorationStyle` property available at the column level. For rows, set the `RowBackgroundStyle` property at the DataGrid level.

### Changing Column Background Color

The `CellDecorationStyle` property allows you to define custom styles for cells within a column. Refer to the [Columns Styling documentation](https://docs.telerik.com/devtools/maui/controls/datagrid/theming-and-styles/columns-styling#celldecorationstyle) for detailed information on column styling.

```xaml
<telerik:DataGridTextColumn.CellDecorationStyle>
    <Style TargetType="telerik:DataGridCellDecorationAppearance">
        <Setter Property="BackgroundColor" Value="LightBlue"/>
    </Style>
</telerik:DataGridTextColumn.CellDecorationStyle>
```

### Changing Row Background Color

To modify the background color of rows, set the `RowBackgroundStyle` property at the DataGrid level. This property applies a background color to all rows in the DataGrid. Detailed information on styling cells and rows can be found in the [Styling documentation](https://docs.telerik.com/devtools/maui/controls/datagrid/theming-and-styles/styling#cells-and-rows).

```xaml
<telerik:RadDataGrid.RowBackgroundStyle>
    <Style TargetType="telerik:DataGridRowBackgroundAppearance">
        <Setter Property="BackgroundColor" Value="LightGreen"/>
    </Style>
</telerik:RadDataGrid.RowBackgroundStyle>
```

By setting these properties, you can achieve a customized appearance for your DataGrid, making it easier to visually distinguish between different rows or columns based on your application's requirements.

## See Also

- [Styling the DataGrid for MAUI](https://docs.telerik.com/devtools/maui/controls/datagrid/theming-and-styles/styling)
- [DataGrid Columns Overview](https://docs.telerik.com/devtools/maui/controls/datagrid/columns/overview)
