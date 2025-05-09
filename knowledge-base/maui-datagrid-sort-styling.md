---
title: Configuring Sort Styling in DataGrid for MAUI
description: Learn how to configure sort styling in the DataGrid for MAUI, including customizing the appearance of the sort indicators.
type: how-to
page_title: Customizing Sort Indicators in MAUI DataGrid
slug: maui-datagrid-sort-styling
tags: datagrid, maui, sort-indicator, header-style, appearance
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.1.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to customize the sort styling in the [DataGrid for MAUI](https://docs.telerik.com/devtools/maui/controls/datagrid/overview). Specifically, I need the entire header to trigger sorting when clicked, and I want to implement the appearance of the sort arrows manually.

This knowledge base article also answers the following questions:
- How do I style sort indicators in MAUI DataGrid?
- How can I customize the appearance of sorting arrows in MAUI DataGrid?
- How to change sorting behavior when clicking the header in MAUI DataGrid?

## Solution

To achieve custom sort styling, configure the exposed properties on the column header style level. Use the following properties to customize the sort appearance:
- `SortIndicatorColor`: Defines the color of the sort indicator.
- `SortIndicatorAscendingText`: Sets the text displayed for ascending sort.
- `SortIndicatorDescendingText`: Sets the text displayed for descending sort.

### Example

Below is an example of setting the sort indicator color in the DataGrid column header style:

```xml
<telerik:RadDataGrid>
    <telerik:RadDataGrid.Columns>
        <telerik:DataGridTextColumn>
            <telerik:DataGridTextColumn.HeaderStyle>
                <Style TargetType="telerik:DataGridColumnHeaderAppearance">
                    <Setter Property="SortIndicatorColor" Value="#FFFFFF" />
                </Style>
            </telerik:DataGridTextColumn.HeaderStyle>
        </telerik:DataGridTextColumn>
    </telerik:RadDataGrid.Columns>
</telerik:RadDataGrid>
```

### Additional Customizations

- Use `SortIndicatorAscendingText` and `SortIndicatorDescendingText` to control the text for ascending and descending sorts.
- Apply these properties in the `<Style>` block targeting `DataGridColumnHeaderAppearance`.

## See Also

- [DataGrid Column Styling Documentation](https://docs.telerik.com/devtools/maui/controls/datagrid/theming-and-styles/columns-styling#sort-indicator-styling)
- [DataGrid Overview](https://docs.telerik.com/devtools/maui/controls/datagrid/overview)
