---
title: Selecting All Text in Edit Mode in DataGrid for UI for .NET MAUI
description: Learn how to select all text in a cell when entering edit mode in the DataGrid for UI for .NET MAUI.
type: how-to
page_title: How to Select All Text in Edit Mode in DataGrid for UI for .NET MAUI
meta_title: How to Select All Text in Edit Mode in DataGrid for UI for .NET MAUI
slug: select-all-text-edit-mode-datagrid-dotnet-maui
tags: datagrid, ui-for-dotnet-maui, selectiononfocus, radentry, edit-mode
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 12.0.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I want to select all text in a cell when entering edit mode in the [DataGrid](https://www.telerik.com/maui-ui/documentation/controls/datagrid/overview) for UI for .NET MAUI, but I can't figure out how to accomplish this.

This knowledge base article also answers the following questions:
- How to use `SelectionOnFocus` property in `RadEntry` for DataGrid editing?
- How to select text automatically in edit mode in DataGrid?
- How to set implicit style for `RadEntry` in DataGrid?

## Solution

To select all text in a cell during edit mode, set the `SelectionOnFocus` property of the `RadEntry` editor to `SelectAll`. Use an implicit style for the `RadEntry` to apply this property.

1. Define an implicit style for `RadEntry` in the `ContentPage.Resources` section.
2. Set the `SelectionOnFocus` property to `SelectAll` within the style.
3. Use the `RadDataGrid` with `UserEditMode` set to `Cell`.

Here is an example implementation:

```xml
<ContentPage.Resources>
    <ResourceDictionary>
        <Style TargetType="telerik:RadEntry">
            <Setter Property="SelectionOnFocus" Value="SelectAll" />
        </Style>
    </ResourceDictionary>
</ContentPage.Resources>

<Grid RowDefinitions="Auto,*" Padding="12">
    <telerik:RadDataPager x:Name="Pager"
                          Source="{Binding Items}"
                          PageSize="10"
                          Grid.Row="0"/>

    <telerik:RadDataGrid Grid.Row="1" x:Name="grid"
                         ItemsSource="{Binding PagedSource, Source={x:Reference Pager}}"
                         AutoGenerateColumns="False"
                         UserEditMode="Cell">
        <telerik:RadDataGrid.Columns>
            <telerik:DataGridTextColumn PropertyName="Id" HeaderText="ID" CanUserEdit="True"/>
            <telerik:DataGridTextColumn PropertyName="Name" HeaderText="Name" CanUserEdit="True"/>
            <telerik:DataGridTextColumn PropertyName="Category" HeaderText="Category" CanUserEdit="False"/>
            <telerik:DataGridTextColumn PropertyName="Price" HeaderText="Price" CanUserEdit="False"/>
            <telerik:DataGridBooleanColumn PropertyName="InStock" HeaderText="In Stock" CanUserEdit="False"/>
        </telerik:RadDataGrid.Columns>
    </telerik:RadDataGrid>
</Grid>
```

## See Also

- [DataGrid Overview for UI for .NET MAUI](https://www.telerik.com/maui-ui/documentation/controls/datagrid/overview)
- [Entry Documentation](https://www.telerik.com/maui-ui/documentation/controls/entry/overview)
- [DataGrid User Edit Modes](https://www.telerik.com/maui-ui/documentation/controls/datagrid/editing)
