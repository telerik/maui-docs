---
title: Disabling Mouse Hover in Telerik DataGrid for .NET MAUI
description: Learn how to disable mouse hover effects in Telerik DataGrid for .NET MAUI by customizing the MouseHoverStyle property.
type: how-to
page_title: How to Disable Mouse Hover Effects in DataGrid for .NET MAUI
meta_title: Disable Mouse Hover in Telerik DataGrid for .NET MAUI
slug: disable-mouse-hover-datagrid-dotnet-maui
tags: datagrid, telerik, .net maui, mousehoverstyle, styling
res_type: kb
---

## Environment

| Version | Control | Author | 
| ------- | ------ | ------ | 
| 11.1.0 | DataGrid for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I want to fully disable mouse hover effects in Telerik [DataGrid for .NET MAUI](https://docs.telerik.com/devtools/maui/controls/datagrid/overview) on Windows.

This knowledge base article also answers the following questions:
- How to remove mouse hover effects in Telerik DataGrid for .NET MAUI?
- Can I make the mouse hover appearance transparent in Telerik DataGrid?
- How to customize the hover style in Telerik DataGrid?

## Solution

To disable mouse hover effects in Telerik DataGrid for .NET MAUI, customize the `MouseHoverStyle` property by removing the hover appearance. Set the background and border colors to transparent and the border thickness to `0`. Use the following example:

```xml
<telerik:RadDataGrid x:Name="grid">
    <telerik:RadDataGrid.MouseHoverStyle>
        <Style TargetType="telerik:DataGridMouseHoverAppearance">
            <Setter Property="BackgroundColor" Value="Transparent" />
            <Setter Property="BorderColor" Value="Transparent" />
            <Setter Property="BorderThickness" Value="0" />
        </Style>
    </telerik:RadDataGrid.MouseHoverStyle>
</telerik:RadDataGrid>
```

## See Also

- [Mouse Hover Style Documentation](https://docs.telerik.com/devtools/maui/controls/datagrid/cells/mouse-hover-cell)
- [Overview of Telerik DataGrid for .NET MAUI](https://docs.telerik.com/devtools/maui/controls/datagrid/overview)
- [Styling Telerik DataGrid for .NET MAUI](https://docs.telerik.com/devtools/maui/controls/datagrid/theming-and-styles/styling)
