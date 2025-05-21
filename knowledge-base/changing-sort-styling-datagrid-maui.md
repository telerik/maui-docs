---
title: Changing Sort Styling in DataGrid for MAUI
description: Learn how to customize the header styling and sort indicator appearance in DataGrid for MAUI to meet specific requirements.
type: how-to
page_title: Customizing Sort Styling and Indicator in DataGrid for MAUI
slug: changing-sort-styling-datagrid-maui
tags: datagrid, maui, sort, styling, sortindicatorcolor, sortindicatorascendingtext, sortindicatordescendingtext
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I need to change the header styling in DataGrid for MAUI when sorting is enabled. Specifically, I want the entire header to trigger sorting when clicked and customize the appearance of the sort arrows to match our design requirements.

This knowledge base article also answers the following questions:
- How to style the header of DataGrid for MAUI with custom sort indicators?
- How to change the appearance of the sort arrows in DataGrid for MAUI?
- How to set custom text for the sort indicators in DataGrid for MAUI?

## Solution

To change the header styling and customize the appearance of the sort indicator in the [DataGrid for MAUI](https://docs.telerik.com/devtools/maui/controls/datagrid/overview), follow these steps:

### Styling the Header and Sort Indicator

Use the `SortIndicatorColor` property to set the color of the sort indicator in the column header. Additionally, use `SortIndicatorAscendingText` and `SortIndicatorDescendingText` to define custom text or icons for the sort indicators.

Example:
```xaml
<telerik:RadDataGrid x:Name="dataGrid" AutoGenerateColumns="False">
    <telerik:RadDataGrid.Columns>
        <telerik:DataGridTextColumn PropertyName="Country">
            <telerik:DataGridTextColumn.HeaderStyle>
                <Style TargetType="telerik:DataGridColumnHeaderAppearance">
                    <Setter Property="SortIndicatorColor" Value="Blue" />
                    <Setter Property="SortIndicatorAscendingText" Value="{x:Static telerik:TelerikFont.IconAuthor}" />
                    <Setter Property="SortIndicatorDescendingText" Value="{x:Static telerik:TelerikFont.IconAlignCenter}" />
                </Style>
            </telerik:DataGridTextColumn.HeaderStyle>
        </telerik:DataGridTextColumn>
        <telerik:DataGridTextColumn PropertyName="Capital" />
    </telerik:RadDataGrid.Columns>
</telerik:RadDataGrid>
```

### Additional Notes

These properties can be set directly within the `HeaderStyle` of the column to customize its appearance.

## See Also

- [DataGrid for MAUI Theming and Styles](https://docs.telerik.com/devtools/maui/controls/datagrid/theming-and-styles/columns-styling)
- [DataGrid for MAUI Overview](https://docs.telerik.com/devtools/maui/controls/datagrid/overview)
