---
title: Enabling Word Wrap in DataGrid Cells for MAUI
description: Learn how to implement word wrap functionality within cells of the DataGrid for MAUI to display large text data effectively.
type: how-to
page_title: How to Enable Word Wrap in DataGrid Cells in MAUI
slug: datagrid-maui-enable-word-wrap
tags: datagrid, maui, cell, word wrap, text wrap, cellcontenttemplate
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 9.0.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

In scenarios where large text data needs to be displayed inside DataGrid's cells, it becomes necessary to enable word wrap to ensure content visibility and readability. 

This knowledge base article also answers the following questions:
- How can I display long text in DataGrid cells without truncation?
- Is it possible to wrap text within the DataGrid cells?
- How to use `CellContentTemplate` for text wrapping in DataGrid?

## Solution

To enable word wrapping for cell content in a DataGrid, utilize the `CellContentTemplate` feature. This approach allows customizing the cell's content and applying text wrapping by setting the `LineBreakMode` property of a `Label` to `WordWrap`. Below are examples in both XAML and C# demonstrating how to implement this functionality.

### XAML Example

```xaml
<telerik:DataGridTextColumn PropertyName="Name" 
                            Width="130"
                            SizeMode="Fixed"
                            HeaderText="Name">
    <telerik:DataGridColumn.CellContentTemplate>
        <DataTemplate>
            <Label Text="{Binding Name}" 
                   LineBreakMode="WordWrap"
                   VerticalOptions="Center"
                   Margin="5, 0" />
        </DataTemplate>
    </telerik:DataGridColumn.CellContentTemplate>
</telerik:DataGridTextColumn>
```

### C# Example

```csharp
DataGridTextColumn textColumn = new DataGridTextColumn();
DataTemplate template = new DataTemplate(() =>
{
    Label label = new Label();
    label.Text = "This is a very very very long text";
    label.LineBreakMode = Microsoft.Maui.LineBreakMode.WordWrap;
    return label;
});
textColumn.CellContentTemplate = template;
// Add other configurations as needed
radDataGrid.Columns.Add(textColumn);
```

The examples above demonstrate how to modify the `CellContentTemplate` to include a `Label` with its `LineBreakMode` set to `WordWrap`. This modification ensures that long text content within the DataGrid cells wraps accordingly, enhancing readability.

## See Also

- [DataGrid Columns Documentation](https://docs.telerik.com/devtools/maui/controls/datagrid/columns/cell-templates)
- [DataGrid Overview](https://docs.telerik.com/devtools/maui/controls/datagrid/overview)
