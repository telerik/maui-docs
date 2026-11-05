---
title: Handling Keyboard Overlap EditCell in RadDataGrid for .NET MAUI
description: Learn how to handle the keyboard overlapping an editable cell in RadDataGrid for .NET MAUI when it is nested inside a ScrollView.
type: how-to
page_title: Prevent Keyboard Overlap with RadDataGrid in .NET MAUI
meta_title: Prevent Keyboard Overlap with RadDataGrid in .NET MAUI
slug: prevent-keyboard-overlap-datagrid-maui
tags: datagrid, .net maui, keyboard, celleditorstyle, keyboardhelper
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 15.1.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

When using [DataGrid](https://www.telerik.com/maui-ui/datagrid) for .NET MAUI within a ScrollView on iOS, the on-screen keyboard may overlap the cell being edited when the grid is positioned bottom of the page. This can make it difficult to see and interact with the input field.

This knowledge base article also answers the following questions:
- How to prevent the iOS keyboard from hiding input controls in UI for .NET MAUI?
- How to configure the keyboard behavior with DataGrid in a ScrollView?
- How to ensure the edited cell remains visible when the keyboard appears and DataGrid is inside ScrollView?

## Solution

To prevent the keyboard from overlapping the editable cell in DataGrid when the control is inside ScrollView, configure the grid and its cell editor using the `KeyboardHelper` class and `CellEditorStyle`. Follow these steps:

1. Add the `telerik:KeyboardHelper.IsTranslationPivot="True"` property to the editor defined in the `CellEditorStyle`.

2. Set the property `telerik:KeyboardHelper.IsTranslationTarget="True"` on the `RadDataGrid`.

```xml
<ScrollView>
    <telerik:RadDataGrid x:Name="dataGrid"
                          ItemsSource="{Binding DataItems}"
                          AutoGenerateColumns="False"
                          telerik:KeyboardHelper.IsTranslationTarget="True">
        <telerik:RadDataGrid.Columns>
            <telerik:DataGridTextColumn PropertyName="Name">
                <telerik:DataGridTextColumn.CellEditorStyle>
                    <Style TargetType="telerik:DataGridTextCellEditor">
                        <Setter Property="telerik:KeyboardHelper.IsTranslationPivot" Value="True" />
                    </Style>
                </telerik:DataGridTextColumn.CellEditorStyle>
            </telerik:DataGridTextColumn>
        </telerik:RadDataGrid.Columns>
    </telerik:RadDataGrid>
</ScrollView>
```

This setup ensures that the keyboard translation mechanism uses the editor as the pivot element and adjusts the grid's position accordingly.

### Note
If nesting the `RadDataGrid` inside a `ScrollView` is required, provide a definitive width and height for the grid to maintain proper UI virtualization and performance.

## See Also
- [DataGrid Overview](https://www.telerik.com/maui-ui/datagrid)
- [CellEditorStyle Documentation](https://www.telerik.com/maui-ui/documentation/controls/datagrid/theming-and-styles/columns-styling#celleditorstyle)
