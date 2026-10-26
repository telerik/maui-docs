---
title: Troubleshoot DataGrid Selection Styles
page_title: Troubleshoot Selection Border and Text Styles in .NET MAUI DataGrid
description: Understand why DataGrid selection visuals can differ from your style definitions and how to check style assignment, current-cell borders, and inherited resources.
type: troubleshooting
slug: datagrid-troubleshoot-selection-styles
tags: datagrid, .net maui, selectionstyle, border, selected text, basedon, baseresourcekey, styling
res_type: kb
---

## Environment

| Version | Product | Author | 
| ---- | ---- | ---- | 
| 15.1.0 | Telerik UI for .NET MAUI DataGrid |[Desislava Yordanova](https://www.telerik.com/blogs/author/desislava-yordanova)| 

## Description

The DataGrid displays an unexpected selection border or text color even though your style resource contains the expected setters. This does not by itself mean that `SelectionStyle` is ignored.

## Solution

Identify the affected appearance before changing your resource dictionaries.

**1.** Confirm that your style targets `DataGridSelectionAppearance` and is assigned to the DataGrid's `SelectionStyle` property. Defining a keyed style in resources does not assign it to the grid.

**2.** Use `BackgroundColor`, `BorderColor`, and `BorderThickness` in the selection style for the selection highlight. For selected cell text, use `SelectedTextColor` in the column's `CellContentStyle` targeting `DataGridTextCellAppearance`. See [CellContentStyle]({%slug datagrid-columns-styling%}#cellcontentstyle).

**3.** On desktop platforms, distinguish the current-cell border from the selection border. Use `CurrentCellStyle`, targeting `DataGridCurrentCellAppearance`, for the current-cell border. See [Styling the Current Cell]({%slug datagrid-current-cell%}#styling-the-cell).

**4.** For inherited styles, verify the referenced base resource and effective setter values separately from the style assigned to `SelectionStyle`. Compare an inline style, explicit `BasedOn` inheritance, and dynamic `BaseResourceKey` resolution in a minimal reproduction before attributing the result to inheritance.

You do not need to copy a complete theme style merely to assign `SelectionStyle`. If you customize Telerik theme resources, follow [Customizing the Controls' Styles]({%slug theme-component-styles-customization%}) for that workflow. Do not assume that dictionary merge order caused a selection issue without checking which resource and style the grid resolves.

## See Also

- [DataGrid Styling]({%slug datagrid-styling%})