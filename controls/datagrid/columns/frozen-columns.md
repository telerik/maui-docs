---
title: Frozen Columns
page_title: .NET MAUI DataGrid Documentation - Frozen Columns
description: "Frozen columns for Telerik DataGrid for .NET MAUI."
position: 4
slug: datagrid-frozen-columns
---

# .NET MAUI DataGrid Frozen Columns

This article describes the frozen columns feature that DataGrid provides. 

You can pin a column on the left side of the grid by setting the `IsFrozen`(`bool`) property to the column. By default the value is `False`. When setting it to `True` to a concrete column, it makes the column frozen. 

![.NET MAUI DataGrid Frozen Column](../images/frozen-column.png)

Set the column freeze in XAML

```XAML
<telerik:RadDataGrid x:Name="grid" 
                     ItemsSource="{Binding Clubs}" 
                     AutoGenerateColumns="False">
    <telerik:RadDataGrid.Columns>
        <telerik:DataGridTextColumn PropertyName="Name" 
                                    IsFrozen="True"
                                    HeaderText="Name"/>
    </telerik:RadDataGrid.Columns>
</telerik:RadDataGrid> 
```

Set the column freeze programatically

<snippet id='data-grid-frozen-columns-programmatically' />


## Collection of frozen columns

Once a column is frozen, it is added to the `FrozenColumns` collection (read-only collection). The collection can be used only for read-only purposes and cannot be modified. Freezing/Unfreezing of the columns is done only through the `IsFrozen` property of the columns.

## Styling

When there is/are frozen column(s) a Splitter UI is visualized. The spliter UI splits the pinned(frozen) columns from the unpinned(unfrozen). 

You can style the frozen splitter UI using the `FrozenColumnsSplitterStyle`(`Telerik.Maui.Controls.Compatibility.DataGrid.DataGridFrozenColumnsSplitterStyle`) property.

Style the Splitter UI's `Width`, `BackgroundColor`, `BorderColor` and `BorderThickness`.

>important The `FrozenColumnsSplitterStyle` property is a property of the DataGrid. It cannot be set on a specific column.

```XAML
<telerik:RadDataGrid.FrozenColumnsSplitterStyle>
    <telerik:DataGridFrozenColumnsSplitterStyle Width="20"
                                                BorderColor="Gray"
                                                BorderThickness="2"
                                                BackgroundColor="LightBlue"/>
</telerik:RadDataGrid.FrozenColumnsSplitterStyle>
```

![.NET MAUI DataGrid Frozen Column](../images/frozen-column-style.png)

## See Also

- [Picker Column]({%slug datagrid-columns-picker-column %})
- [Template Column]({%slug datagrid-columns-template-column %})
- [Text Column]({%slug datagrid-columns-text-column %})
