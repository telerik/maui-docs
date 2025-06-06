---
title: Removing Tree Indentation in TreeDataGrid for .NET MAUI
description: Learn how to remove the tree indentation in the Telerik TreeDataGrid for .NET MAUI control.
type: how-to
page_title: How to Remove Tree Indentation in Telerik TreeDataGrid for .NET MAUI
slug: remove-tree-indentation-treedatagrid-dotnet-maui
tags: treedatagrid,.net maui,levelindentation,styling
res_type: kb
ticketid: 1689581
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.0 | Telerik UI for .NET MAUI TreeDataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I want to remove the tree indentation in the Telerik [TreeDataGrid](https://docs.telerik.com/devtools/maui/controls/treedatagrid/overview) for .NET MAUI control. This involves customizing the appearance of the `ExpandCollapseIndicator` to eliminate the space allocated for tree levels.

This knowledge base article also answers the following questions:
- How to set `evelIndentation` to zero in TreeDataGrid for .NET MAUI?
- How to customize the `ExpandCollapseIndicatorStyle` in TreeDataGrid?
- How to control indent spacing in Telerik TreeDataGrid for .NET MAUI?

## Solution

To remove the tree indentation, set the `LevelIndentation` property of the `TreeDataGridExpandCollapseIndicatorAppearance` to `0`. Apply this style to the `ExpandCollapseIndicatorStyle` property of the TreeDataGrid.

**1.** Define a style for `TreeDataGridExpandCollapseIndicatorAppearance` in your XAML.

**2.** Set the `LevelIndentation` property value to `0`.

```xaml
<Style x:Key="style" TargetType="telerik:TreeDataGridExpandCollapseIndicatorAppearance">
    <Setter Property="LevelIndentation" Value="0" />
</Style>
```

**3.** Assign this style to the `ExpandCollapseIndicatorStyle` of the TreeDataGrid.

```xaml
<telerik:RadTreeDataGrid x:Name="treeDataGrid"
                         ExpandCollapseIndicatorStyle="{StaticResource style}" />
```

## See Also

- [TreeDataGrid Style]({%slug treedatagrid-styling%})
