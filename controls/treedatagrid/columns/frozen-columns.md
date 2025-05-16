---
title: Frozen Columns
page_title: .NET MAUI TreeDataGrid  Documentation - Frozen Columns
description: Learn how to freeze columns in Telerik TreeDataGrid for .NET MAUI.
position: 4
slug: treedatagrid-frozen-columns
---

# .NET MAUI TreeDataGrid Frozen Columns

This article describes the frozen columns feature that the [.NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) provides. 

You can pin a column on the left side of the grid by setting the `IsFrozen`(`bool`) property to the column. By default the value is `False`. When setting it to `True` to a concrete column, it makes the column frozen. 

The next example shows how to set the frozen columns in XAML:

```XAML
<telerik:RadTreeDataGrid x:Name="grid" 
                         ItemsSource="{Binding Clubs}" 
                         AutoGenerateColumns="False">
    <telerik:RadDataGrid.Columns>
        <telerik:DataGridTextColumn PropertyName="Name" 
                                    IsFrozen="True"
                                    HeaderText="Name"/>
    </telerik:RadDataGrid.Columns>
</telerik:RadTreeDataGrid> 
```

## Collection of Frozen Columns

Once a column is frozen, it is added to the `FrozenColumns` collection (read-only collection). The collection can be used only for read-only purposes and cannot be modified. Freezing/Unfreezing the columns is done only through the `IsFrozen` property of the columns.

## Styling

When there is a frozen column, a splitter UI is visualized. The splitter UI splits the frozen columns from the unfrozen.

You can style the frozen splitter UI using the `FrozenColumnsSplitterStyle`(`Telerik.Maui.Controls.DataGrid.DataGridFrozenColumnsSplitterStyle`) property. The `FrozenColumnsSplitterStyle` property is a property of the DataGrid. It cannot be set on a specific column.

The next example shows how to style the splitter UI by using the `Width`, `BackgroundColor`, `BorderColor` and `BorderThickness` properties of the FrozenColumnsSplitterStyle class.

```XAML
<telerik:RadDataGrid.FrozenColumnsSplitterStyle>
    <telerik:DataGridFrozenColumnsSplitterStyle Width="8"
                                                BorderColor="Gray"
                                                BorderThickness="2"
                                                BackgroundColor="LightBlue"/>
</telerik:RadDataGrid.FrozenColumnsSplitterStyle>
```

## See Also

- [Columns Cells Templates]({%slug treedatagrid-cell-templates%})
- [Column Resizing]({%slug treedatagrid-column-resizing%})
- [Columns Width]({%slug treedatagrid-columns-width%})
- [Frozen Columns]({%slug treedatagrid-frozen-columns%})
- [Columns Reordering]({%slug treedatagrid-columns-reordering%})
